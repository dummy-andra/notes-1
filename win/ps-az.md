# PowerShell commands for Azure

#### Install the Azure Resource Manager PowerShell module
The older module __AzureRM__ has been replaced, largely, by __Az__. Commands to the older module are aliased to the new, but there are some commands which require the older module.
```powershell
Install-Module -Name Az -AllowClobber
Install-Module AzureRM
```

#### Connect to Azure 
`Connect-AzAccount` will produce an alphanumeric code that you must enter on [Microsoft's website](https://microsoft.com/devicelogin) to complete authentication.

```powershell
Connect-AzAccount
```

#### Create a Resource Group
`New-AzResourceGroup` has two required parameters
  - `-Name` which can be defined positionally at position __0__
  - `-Location`, the geographic area ("EastUS", "CentralUS", etc), defined positionally at position __1__

#### Create a VM
`New-AzVM`
```powershell
New-AzVM -ResourceGroupName "RG" -Name "VM" -Location "EastUS" -Size "Standard-B2s" -Credential (Get-Credential)
```

The `-Image` optional named parameter can be used to define other operating systems, and requires friendly image names. If a Linux image is provided, you should provide the `-Linux` switch parameter as well in order to specify a Linux-type disk file.
  - Win2016Datacenter (default)
  - Win2012R2Datacenter
  - Win2012Datacenter
  - Win2008R2SP1
  - UbuntuLTS
  - CentOS
  - CoreOS
  - Debian
  - openSUSE-Leap
  - RHEL
  - SLES

A custom image object can be built up and passed to `New-AzVM` through the `-VM` named parameter by using other commands:
```powershell
...
$vm = New-AzVMConfig -VMName $VMName -VMSize $VMSize
$vm = Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $ComputerName -Credential $Credential -Provision VMAgent -EnableAutoUpdate
$vm = Add-AzVMNetworkInterface -VM $vm -Id $NIC.Id
$vm = Set-AzVMSourceImage -VM $vm -PublisherName 'MicrosoftWindowsServer' -Offer 'WindowsServer' -Skus '2012-R2-Datacenter' -Version latest

New-AzVM -ResourceGroupName $ResourceGroupName -Location $LocationName -VM $vm
```

#### Find a Marketplace image

`Get-AzVMImage` requires the following named parameters:
  - `-Location` i.e. "EastUS"
  - `-Offer` cf. `Get-AzVMImageOffer`
  - `-PublisherName` cf. `Get-AzVMImagePublisher`
  - `-Skus` cf. `Get-AzVMImageSku`
  - `-Version` providing `*` will produce a list of available versions

`Get-AzVMImageOffer`
  - `-Location`
  - `-PublisherName`
`Get-AzVMImagePublisher`
  - `-Location`
`Get-AzVMImageSku`
  - `-Location`
  - `-Offer`
  - `-PublisherName`


#### Start a VM

`Start-AzVM` requires at minimum __2__ arguments:
Option              | Mandatory | Position
:---                | :--- | :---
`-Id`, `-ResourceGroupName` | ✔ | 0
`-Name`             | ✔ | 1

```powershell
Start-AzVM Greeks Socrates
```

#### Shut down a VM
```powershell
Stop-AzVM RG VM
```

#### Connect to VM from a Windows machine
1. WinRM access must be enabled on the target VM as well as the local machine.
```powershell
Enable-PSRemoting
```
Alternatively:
```cmd
winrm quickconfig
```

It can also be done through Azure, using `Invoke-AzVMRunCommand -CommandId EnableRemotePS`


2. __Modify Network Security Group policy__ (see below) to allow inbound connections to ports 5985 and 5986, which are used by WinRM.

3. Add the VM's public IP address &lt;$ipaddr&gt; to the trusted hosts of the local machine (must be run as administrator):
```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value ipaddr
```

4. Open the WinRM ports in the VM's firewall, if Windows Firewall is activated. The commands provided here can be run locally on the VM, or invoked through Azure:

```powershell
New-NetFirewallRule -DisplayName "WinRMHTTP" -Direction Inbound -LocalPort 5985 -Protocol TCP -Action Allow
New-NetFirewallRule -DisplayName "WinRMHTTPS" -Direction Inbound -LocalPort 5986 -Protocol TCP -Action Allow
```

Alternatively:

```cmd
netsh advfirewall firewall add rule name=WinRMHTTP dir=in action=allow protocol=TCP localport=5985
netsh advfirewall firewall add rule name=WinRMHTTPS dir=in action=allow protocol=TCP localport=5986
```

5.  Connect to the VM's public IP, passing along a previously-stored credential:
```powershell
$cred=Get-Credential
Enter-PSSession -ComputerName 123.47.78.90 -Credential $cred
```

Or, enter the credential dynamically
```powershell
etsn -ComputerName 123.45.67.89 -Credential (Get-Credential)
```

##### Connect to VM from a Mac or Linux machine
Using OpenSSH...

#### Display Azure subscription ID
```powershell
Get-AzSubscription | select -ExpandProperty Id
```

#### Invoking a command on a VM
`Invoke-AzVMRunCommand` requires only a single option: `-CommandId`. You can pass along a script containing predefined commands using the named parameter `-ScriptPath`, but the value for `-CommandId` must be `RunPowerShellScript`. Unlike `Invoke-Command, there is no way to define commands inline.
```powershell
Invoke-AzVMRunCommand -ResourceGroupName RG -VMName VM -CommandId 'RunPowerShellScript' -ScriptPath C:\injectedscript.ps1
```

#### Modify Network Security Group policies
Open inbound ports are most easily defined at the time of VM creation (`New-AzVM ... -OpenPorts 5985,5986 ...`).

From __Azure Portal__: Virtual machines > VM to be modified > (Settings) Networking > Network interface > Add inbound port rule button 

In PowerShell, an __inbound security rule__ can be created:
```powershell
Get-AzNetworkSecurityGroup -Name NSG -ResourceGroupName 4SysOps | 
Add-AzNetworkSecurityRuleConfig
  -Name AllowingWinRMHTTP -Description "To Enable PowerShell Remote Access"
  -Access Allow -Protocol Tcp -Direction Inbound -Priority 103 
  -SourceAddressPrefix Internet -SourcePortRange * 
  -DestinationAddressPrefix * -DestinationPortRange 5985 | 
Set-AzNetworkSecurityGroup
```

#### Display IP address
`Get-AzPublicIpAddress` takes the name of the resource (e.g. where &lt;VM&gt; is the name of the virtual machine, "VM-ip") and returns an object with a property `IpAddress`
```powershell
Get-AzPublicIpAddress Socrates-ip | select IpAddress
```

In order to use the output in an evaluated expression (like command substitution in bash), the property has to be expanded with the `-ExpandProperty` switch.
```powershell
Get-AzPublicIpAddress Socrates-ip | select -ExpandProperty IpAddress
```

## Sources
  - "Enable-PSRemoting". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-6)
  - "Azure Az Module for Windows PowerShell, Core, and Cloud Shell Replaces Azure RM". [Petri](https://www.petri.com/azure-az-module-for-windows-powershell-core-and-cloud-shell-replaces-azurerm): 2019/01/23.
  - "Manage Azure IaaS virtual machines with Windows Admin Center". [Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/azure/manage-azure-vms): 2018/09/06.
  - "PowerShell Basics: Filtering Objects". [ITPro Today](https://www.itprotoday.com/powershell/powershell-basics-filtering-objects): 2013/07/25.
  - "Connect to Azure VM using PowerShell". [4sysops](https://4sysops.com/archives/connect-to-azure-vm-using-powershell/): 2018/10/11.
  - "About PSSessions". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-6): 2019/07/02.
  - "Enable PowerShell Remoting". [4sysops](https://4sysops.com/wiki/enable-powershell-remoting/).
  - "Start-AzureRmVM". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/start-azurermvm?view=azurermps-6.13.0).
  - "Invoke-AzureRmVMRunCommand". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/AzureRm.Compute/Invoke-AzureRmVMRunCommand?view=azurermps-6.13.0).
  - "PowerShell Remoting over SSH". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core?view=powershell-6): 2018/08/13.
  - "Installation of OpenSSH for Windows Server 2019 and Windows 10". [Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse): 2019/01/06.
  - "New-AzVM". [Microsoft Docs](https://docs.microsoft.com/en-us/powershell/module/az.compute/new-azvm?view=azps-2.4.0).