# PowerShell
#### Table of contents
\#    | Cmdlet nouns sorted alphabetically
---   | ---
A     | **`Alias`** [`Export`](#export-alias) [`Get`](#get-alias) [`New`](#new-alias )[`Set`](#set-alias) &bull; **`Archive`** [`Expand`](#expand-archive)
C     | **`ChildItem`** [`Get`][Get-ChildItem] **`Clipboard`** [`Get`](#get-clipboard) [`Set`](#set-clipboard) &bull; **`Computer`** [`Add`](#add-computer) &bull; **`Credential`** [`Get`](#credentials) **`Csv`** [`Export`][Export-Csv] [`Import`][Import-Csv]
D     | **`Disk`** [`Get`](#get-disk)
E     | **`ExecutionPolicy`** [`Set`][Set-ExecutionPolicy]
G     | **`Guid`** [`New`](#new-guid)
H     | **`Help`** [`Get`](#get-help) [`Update`](#update-help)
L     | **`List`** [`Format`][Format-List] &bull; **`Location`** [`Set`][Set-Location]
M     | **`Module`** [`Import`](#module) [`Install`](#module)
N     | **`NetAdapter`** [`Get`][Get-NetAdapter] **`NetFirewallRule`** [`Get`](#get-netfirewallrule) [`New`](#new-netfirewallrule) [`Set`](#set-netfirewallrule) &bull; **`NetIpAddress`** [`New`][New-NetIpAddress] &bull; **`Null`** [`Out`][Out-Null]
O     | **`Object`** [`ForEach`][ForEach-Object] [`Select`][Select-Object] [`Where`][Where-Object] **`Output`** [`Write`](#write-output)
P     | **`Partition`** [`Get`](#get-partition) [`New`](#new-partition) [`Remove`](#remove-partition) &bull; **`PSReadlineOption`** [`Get`](#get-psreadlineoption) [`Set`](#set-psreadlineoption) &bull; **`PSSession`** [`Disconnect`][Disconnect-PSSession] [`Enter`](#enter-pssession) [`Exit`](#exit-pssession) [`Get`](#get-pssession) [`New`][New-PSSession]
S     | **`Service`** [`Get`](#service) [`Start`](#service) [`Stop`](#service) &bull;
T     | **`Table`** [`Format`][Format-Table]
V     | **`VMFirmware`** [`Set`][Set-VMFirmware] &bull; **`VMMemory`** [`Set`](#set-vmmemory) &bull; **`VMNetworkAdapter`** [`Set`](#set-vmnetworkadapter) &bull; **`VMProcessor`** [`Set`](#set-vmprocessor) &bull; **`VMSwitch`** [`New`][New-VMSwitch]
W     | **`WebRequest`** [`Invoke`](#invoke-webrequest) &bull; **`WindowsFeature`** [`Get`](#get-windowsfeature) [`Install`](#install-windowsfeature) **`WMIObject`** [`Get`](#get-wmiobject)

\#    | Active Directory cmdlets
---   | ---
A     | **`ADAccount`** [`Search`](#search-adaccount) [`Unlock`](#unlock-adaccount) &bull; **`ADAccountPassword`** [`Set`](#set-adaccountpassword) 
D     | **`ADDSDomain`** [`Install`](#install-addsdomain) &bull; **`ADDSDomainController`** [`Uninstall`](#uninstall-addsdomaincontroller) &bull; **`ADDSForest`** [`Get`](#get-adforest) [`Install`](#install-addsforest) 
O     | **`ADObject`** [`Set`](#set-adobject) &bull; **`ADOrganizationalUnit`** [`Get`](#get-adorganizationalunit) [`New`](#new-adorganizationalunit) [`Remove`](#remove-adorganizationalunit) [`Set`](#set-adorganizationalunit)
U     | **`ADUser`** [`Get`](#get-aduser) [`New`](#new-aduser) 

Topic                 | Cmdlets
---                   | ---
Clipboard             | [`Get-Clipboard`](#get-clipboard) [`New-Guid`](#new-guid) [`Set-Clipboard`](#set-clipboard) [`Write-Output`](#write-output)
Disk management       | [`Format-Volume`](#format-volume) [`Get-Disk`](#get-disk) [`Get-Partition`](#get-partition) [`New-Partition`](#new-partition) [`Remove-Partition`](#remove-partition)
Environment           | [`Get-Module`][Get-Module] [`Import-Module`][Import-Module] [`Set-ExecutionPolicy`][Set-ExecutionPolicy] [`Set-Location`][Set-Location]
Filters               | [`Where-Object`][Where-Object] [`Select-Object`][Select-Object] [`Select-String`](#filters) [`Out-GridView`](#filters) [`ForEach-Object`][ForEach-Object]
Firewall              | [`Get-NetFirewallRule`](#get-netfirewallrule) [`New-NetFirewallRule`](#new-netfirewallrule) [`Set-NetFirewallRule`](#set-netfirewallrule)
Formatting            | [`Format-List`][Format-List] [`Format-Table`][Format-Table] [`Format-Wide`](#output-formatting)
Hyper-V               | [`New-VMSwitch`][New-VMSwitch] [`Set-VMFirmware`][Set-VMFirmware] [`Set-VMMemory`](#set-vmmemory) [`Set-VMNetworkAdapter`](#set-vmnetworkadapter) [`Set-VMProcessor`](#set-vmprocessor)
Remote administration | [`Enable-PSRemoting`][Enable-PSRemoting] [`Invoke-Command`](#invoke-command) &bull; **`PSSession`** [`Disconnect`][Disconnect-PSSession] [`Enter`][Enter-PSSession] [`Exit`](#exit-pssession) [`Get`](#get-pssession) [`New`][New-PSSession]
System administration | [`Get-Alias`][Get-Alias] [`Get-Command`][Get-Command] [`Get-Help`][Get-Help] [`Get-History`][Get-History] [`Get-Module`][Get-Module] `Get-Process` `Get-PSDrive` [`Get-Service`][Get-Service] [`Update-Help`][Update-Help]

## Syntax
The `Throw` keyword generates a terminating error

#### Variables
**Automatic variables** are variables that store state information for PowerShell and are created and maintained by Powershell.

Syntax          | Effect
:---            | :---
`$_` `$PSItem`  | **pipeline object** current object in the pipeline object
`$?`            | execution status of the last operation
`$^`            | first token in the last line received by the session
`$$`            | last token in the last line received by the session

Variables can be typed by preceding their identifier with the datatype in brackets
```powershell
[double]$Price
[int]$Quantity
[string]$Description
```
Compatible data can be **cast** or converted by simply specifying the type in an assignment, but when the data cannot be converted the interpreter will throw an error.
```powershell
$Number = [int]'04'
$FailedCast = [int]'Hello'
```

#### Profiles
Syntax                            | Effect
:---                              | :---
`$profile`                        | display file of current profile
`$profile.CurrentUserCurrentHost` | %UserProfile%\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
`$profile.CurrentUserAllHosts`    | %UserProfile%\Documents\WindowsPowerShell\profile.ps1
`$profile.AllUsersAllHosts`       | %windir%\System32\WindowsPowerShell\v1.0\profile.ps1
`$profile.AllUsersCurrentHost`    | %windir%\System32\WindowsPowerShell\v1.0\Microsoft.PowerShell_profile.ps1

#### Comparison operators
Syntax          | Effect
---             | ---
`-like`         | wildcard pattern
`-match`        | regex pattern
`-is`           | type comparison

Syntax                        | Effect
:---                          | :---
`Get-Alias Definition -eq Get-ChildItem`|display items that point to `Get-ChildItem`
`Get-Command \| measure`      | piping to `measure` is similar to `wc`, will count lines
`Get-Command -Module ActiveDirectory`|display cmdlets available under a specified module
`Get-Command *smb*`           | use a wildcard
`Get-Module -ListAvailable`   | display installed PowerShell modules
`Invoke-History`              | run a command from the history
`New-Alias ip Get-NetIPAddress`|establish a new alias
`Set-Alias ip Get-NetAdapter` |edit an existing alias
`New-PSDrive -Name scripts -PSProvider FileSystem -Root "C:\Scripts"`|map a directory to a drive
`Remove-PSDrive -Name scripts`|remove a drive

Common Parameter              | Effect
:---                          | :---
`-Debug`,`-db`                | display programmer-level detail about command operation
`-ErrorAction`                | determine how the cmdlet responds to a non-terminating error
`-ErrorVariable`,`-ev`        | store errors in specified variable
`-InformationAction`,`-infa`  | specify action to take at occurrences of `Write-Information` command
`-InformationVariable`,`-iv`  | store information message passed from `Write-Information` cmdlet
`-OutVariable`,`-ov`          | store output objects from the command in the specified variable
`-OutBuffer`,`-ob`            | determine number of objects to accumulate in a buffer before any objects are sent through the pipeline
`-PipelineVariable`,`-pv`     | store value of the current pipeline element in specified variable
`-Verbose`,`-vb`              | display detailed operation done by the command
`-WarningAction`,`-wa`        | specify action to take on occurrence of `Write-Warning` cmdlet
`-WarningVariable`,`-wv`      | store warnings about the command in a variable
`-WhatIf`,`-wi`               | display a message describing the effect of the command, instead of actually executing it
`-Confirm`,`-cf`              | prompt for confirmation before executing the command

## Tasks
#### Comparison with bash
Bash            | PowerShell | Notes
:---            | :---       | :---
\\              | \`         | used at the end of lines to allow multiline commands
`$!` `!$`       | `$$` | automatic variable referring to the last "token" (argument) in the previous command
`$?`            | `$?` | automatic variable containing the execution status of the previous command
`&`             | `Start-Job`,`sajb` | sends a process into the background
`>>`            | `Add-Content`, `ac`
`alias`         | `Get-Alias`, `gal`; `New-Alias`, `nal`
`awk`           | `Select-Object`, `select` | See __Filters__ below
`bzip2`         | `Compress-Archive`, `Expand-Archive`
`cat`           | `Get-Content`, `cat`, `gc`, `type` 
`cp`            | `Copy-Item`, `cp`, `cpi`, `copy`
`cd`            | `Set-Location`, `cd`, `sl`, `chdir`
`echo`          | `Write-Host`
`find`          | `Get-ChildItem -Recurse -File -Filter ...`
`grep`          | `Where-Object`, `where`, `?` | See __Filters__ below
`gzip`          | `Compress-Archive`, `Expand-Archive`
`less` `more`   | `Out-Host -Paging`, `oh -Paging`
`man`           | `Get-Help`
`ls`            | `Get-ChildItem`, `dir`, `gci`, `ls` 
`mkdir`         | `New-Item -ItemType Directory`, `ni -ItemType Directory`
`print`         | `Write-Host`
`printf`        | `Write-Host`
`pwd`           | `Get-Location`, `gl`, `pwd`
`reset`         | `Clear-Host`, `clear`, `cls` 
`rm`            | `Remove-Item`, `rm`, `ri`, `rmdir`, `rd`, `del`
`sed`           | `Where-Object`, `where`, `?` | See __Filters__ below
`shutdown -r`   | `Restart-Computer`
`shutdown`      | `Stop-Computer`
`tail`          | `Get-Content -Tail`
`touch`         | `New-Item`
`uniq`          | `Select-Object -Unique`
#### Filters
Filtering results can be done with 5 commands:
- `Where-Object` (aliased to `where` and `?`): the most commonly used such command
- `Select-Object` (aliased to `select`): used to specify specific columns of information to be displayed
- `Select-String` (aliased to `sls`)
- `Out-GridView`
- `ForEach-Object` (aliased to `foreach` and `%`) There are two different ways to construct a `ForEach-Object` statement:
  1. __Script block__, within which the variable `$_` represents the current object
  2. __Operation statement__, more naturalistic, where you specify a property value or call a method.
#### Credentials
Credentials can be stored in a variable and built interactively with `Get-Credential`
```powershell
$cred = Get-Credential
```
A credential can be built piecemeal by first securely saving a password with `ConvertTo-SecureString`
```powershell
$pw = ConvertTo-SecureString "Password" -AsPlainText -Force
```
Then construct the credential by using `New-Object`
```powershell
$cred = New-Object System.Management.Automation.PSCredential ("FullerP", $pw)
```
### Output formatting
Change output format to `Format-Wide`
```powershell
Get-Service | Format-Wide
```
Change output format to be a single column
```powershell
Get-Service | Format-Wide -Column 1
```
Change output to display the `DisplayName` property
```powershell
Get-Service | Format-Wide -Property DisplayName
```
Display output as a list with properties listed next to values
```powershell
Get-Service | Format-List
```
Display all properties
```powershell
Get-Service | Format-List -Property *
```
Display only specified properties
```powershell
Get-Service | fl -Property Status,StartType,DisplayName
```
Display all properties
```powershell
Get-Service | Format-Table -Property *
```
Group by `Status`, but the output will be confused because it was not sorted
```powershell
Get-Service | Format-Table -Property DisplayName,StartType,Status -GroupBy Status
```
Sort list of services
```powershell
Get-Service | Sort-Object
```
Group by `Status` after sorting
```powershell 
 Get-Service | Sort-Object -Property Status | Format-Table -Property DisplayName,StartType,Status -GroupBy Status
```
Will produce an error because `Write-Host` expects a single object
```powershell
Get-Service | Write-Host
```
Loop through each object in output of `Get-Service` and send the `name` field to `Write-Host`
```powershell
Get-Service | ForEach-Object {Write-Host $_.name}
```
### File manipulation
Create a new file in the current working directory named `filename`
```powershell
New-Item -ItemType File -Name filename
```
Append `content` to `file`
```powershell
Add-Content C:\path\to\file $content
```
### Hash tables
**Hash tables** (equivalent to Python dictionaries) can be built with hash literals:
```powershell
$hashtable = @{
  Apple = 'red'
  Orange = 'orange'
  Eggplant = 'purple'
}
```
Each line in a hash literal is a separate statement, that needs to be separated by semicolons when written in-line:
```powershell
$hashtable = @{ Apple = 'red'; Orange = 'orange'; Eggplant = 'purple' }
```
The Hashtable method `Add()` can also be used:
```powershell
$hashtable = @{}
$hashtable.Add('Apple','red')
$hashtable.Add('Orange','orange')
$hashtable.Add('Kiwi','green')
```
Like dicts in Python, copying a hash table is merely a reference or shallow copy:
```powershell
$hashtable1 = $hashtable
$hashtable1['Apple'] = 'rainbow'
$hashtable['Apple'] # => rainbow
```
But a deep copy or "clone" can be made:
```powershell
$hashtable2 = $hashtable.Clone()
```
Like in Python, the keys and values can be retrieved with methods (properties in PowerShell)
```powershell
$hashtable.Keys # => @('Apple','Orange','Kiwi')
$hashtable.Values # => @('red','orange','green')
```
Unlike Python, a hash table can be made ordered, changing its data type:
```powershell
$Hashtable = [ordered]@{One = 1; Two = 2; Three = 3; Four = 4}
$Hashtable.GetType().Name # => OrderedDictionary
```
Measuring length:
```powershell
$Hashtable.Count
```
Removing keys:
```powershell
$Hashtable.Remove('One')
```
### Scripting
Functions are declared with the following syntax
```powershell
function Start-PSAdmin {
  Start-Process PowerShell -Verb RunAs
}
```
Single-line comments are preceded by `#`. But block quotes can be created by enclosing them between `<#` and `#>`.\
__Positional parameters__ can be referenced using the built-in array `args`, which contains all arguments passed to the function on invocation.
```powershell
function Get-LargeFiles {
  Get-ChildItem C:\Users\Michael\Documents |
  where {$_.Length -gt $args[0] and !$_PSIscontainer} |
  Sort-Object Length -Descending
}
```
__Named parameters__ can be declared in one of two ways. One, within the function body using the `param` keyword, followed by the name of the variable representing the parameter's value, enclosed in `$(...)`:
```powershell
function Get-LargeFiles {
  param ($Size)
  Get-ChildItem C:\Users\Michael\Documents |
  where {$_.Length -gt $Size -and !$_.PSIsContainer} |
  Sort-Object Length -Descending
}
```
An alternative way is directly after the function name, with each parameter separated by a comma.
```powershell
function Get-LargeFiles($Size) {
  Get-ChildItem C:\Users\Michael\Documents |
  where {$_.Length -gt $Size -and !$_.PSIsContainer} |
  Sort-Object Length -Descending
}
```
Default values for parameters can be specified by placing them within the parentheses
```powershell
function Get-LargeFiles {
  param ($Size=2000)
  Get-ChildItem C:\Users\Michael\Documents |
  where {$_.Length -gt $Size -and !$_.PSIsContainer} |
  Sort-Object Length -Descending
}
```
The name of the variable becomes the named parameter used when invoking the function
```powershell
Get-LargeFiles -Size 2000
```
__Data typing__ can be performed by preceding the named parameter with `[int]`, for example. This simplifies data validation and also serves to document your code.
```powershell
function Get-LargeFiles {
  param ([int]$Size=2000)
  Get-ChildItem C:\Users\Michael\Documents |
  where {$_.Length -gt $Size -and !$_.PSIsContainer} |
  Sort-Object Length -Descending
}
```
__Switch parameters__ are declared with a special syntax, such that `[switch]` precedes the dollar sign.
```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```
Passing the option `-on` to the function on invocation will produce the output:
```
Switch on
```
Omitting the option:
```
Switch off
```
Boolean values can be explicitly set upon invocation using this syntax:
```powershell
Switch-Item -on:$false
```
Which will produce the output:
```
Switch off
```
__Mandatory parameters__ are declared by preceding the parameter name with `[Parameter(Mandatory=$true)]`. 
```powershell
```
### Control flow
```powershell
if ($condition) {
  ...
}
```
```powershell
switch ($reference) {
  $value1 { ... }
  $value2 { ... }
}
```
### Loops
Pipeline is the defining feature of PowerShell, which allows it to break apart composite objects and act on each element with the `ForEach-Object` cmdlet.
```powershell
1..5 | ForEach-Object {$_ + 2} # => @(3,4,5,6,7)
```
When values are stored in a variable at the end of a pipeline, it will create an array. `while` and `do while` loops are available, as well as `until` and `do until` loops which operate so long as their condition is **false**.
```powershell
$Values = while ($true) {(++$Tick); if ($Tick -gt 2) { break } } # => @(1,2,3)
$Values = do { 'eat me!' } while ($false) # => @('eat me!')
```

## Cmdlets
### `Add-Computer`
Join a computer to a domain [[^][Zacker]: 20]

Option  | Description
---     | ---
`Credential`
`DomainName`
`NewName`

Rename a computer and join it to a domain
```powershell
Add-Computer -DomainName adatum.com -NewName ServerB -Credential adatum\administrator
```
Join a new computer to a domain [^][1]
```powershell
Add-Computer -Domain 'officeprodemoco.onmicrosoft.com' -Restart
New-ADComputer -Name "O365-CL93"
```
Joining many computers using a .csv file
```powershell
New-ADComputer -Name "O365-CL93"
$List = "C:\Labfiles\computers.csv"
$OU = "OU=office365,DC=officeprodemoco,DC=onmicrosoft,DC=com"
Import-Csv -path $List | ForEach-Object {New-ADComputer -Name $_.Name -Path $OU}
```
Verify a computer has connected to a domain
Check "Organization" in Windows about page, or navigate to Control PAnel > System and Security > System and examine the **Computer name, domain, and workgroup settings**, where the domain can be seen.
### `Add-PSSnapin`
### `Disconnect-PSSession`
Terminate a remote PowerShell session begun with [`New-PSSession`][New-PSSession] [[^][Zacker]: 22]
### `Enable-PSRemoting`
### `Enter-PSSession`
Interact with the specified PowerShell session
```powershell
Enter-PSSession -id 1
```
Start and enter a new PS session to specified computer with provided credentials. This will change the prompt to show the name of the remote machine in brackets.
```powershell
Enter-PSSession -ComputerName o365-dc01 -Credential officeprodemoco\joey
```
### `Exit-PSSession`
Exit a remote PowerShell session [[^][Zacker]: 22]\
End the PowerShell session with the specified computer
```powershell
Exit-PSSession -ComputerName demodc
```
### `Expand-Archive`
Decompress archives
```powershell
Expand-Archive
```
### `Export-Alias`
Export session aliases to a ".ps1" file
```powershell
Export-Alias -Path alias.ps1 -As Script
```
### `Export-Csv`
### `Export-CliXml`
### `Format-Volume`
Full format of specified drive [^][16]
```powershell
Format-Volume -DriveLetter S -FileSystem FAT32 -NewFileSystemLabel SumTips -Full
```
### `Get-Alias`
Display aliases
```powershell
Get-Alias
```
Display items that point to `Get-ChildItem`
```powershell
Get-Alias -Definition Get-ChildItem
```
### `Get-ChildItem`
### `Get-Clipboard`
Interpret items in clipboard as files
```powershell
Get-Clipboard -Format FileDropList
```
Retrieve various properties of an image in clipboard
```powershell
Get-Clipboard -Format Image
```
### `Get-Command`
### `Get-Disk`
### `Get-Help`
Option            | Effect
---               | ---
`-Examples`       | display usage examples
`-Detailed`       | display detailed help for a command
`-Full`           | display entire help file for a command
`-Online`         | navigate to online help page for a command
`-ShowWindow`     | display help output in a window
### `Get-Member`
### `Get-Module`
### `Get-NetAdapter`
Display available network interfaces [[^][Zacker]: 19]

Option  | Description
---     | ---
...
### `Get-NetFirewallRule`
Display all firewall rules
```powershell
Get-NetFirewallRule
```
Display active firewall rules for inbound connections
```powershell
Get-NetFirewallRule -Enabled True -Direction Inbound
```
Display programs associated with firewall rules
```powershell
Get-NetFirewallRule | %{$_.Name; $_ | Get-NetFirewallApplicationFilter}
```
### `Get-Partition`
Display a list of existing partitions, their drive letters, and the disk they are associated with [^][16]
```powershell
Get-Disk | Get-Partition
```
### `Get-PSReadlineOption`
Display options available in the module
```powershell
Get-PSReadlineOption
```
### `Get-PSSession`
Display PowerShell sessions
```powershell
Get-PSSession
```
### `Get-Service`
Display status of &lt;WinRM&gt; service
```powershell
Get-Service WinRM
```
```powershell
gsv winrm
```
### `Get-WindowsFeature`
Display installable Windows roles, role services, and features
Display a branching view of available Windows roles, role services, and features
```powershell
Get-WindowsFeature
```
### `Get-WmiObject`
View system uptime
```powershell
Get-WmiObject -Win32_OperatingSystem -ComputerName localhost |
Select-Object -Property @{n="Last Boot Time";e={[Management.ManagementDateTimeConvert]::ToDateTime($_.LastBootUpTime)}}
```
### `Import-CliXml`
### `Import-Csv`
Add a CSV full of users
```powershell
Import-Csv users.csv | foreach { New-ADUser -SamAccountName $_.SAM -GivenName $_.Last -DisplayName $_.DisplayName -Name $_.Name -Description $_.Description -Enabled $True -AccountPassword (ConvertToSecureString $_.Password -AsPlainText -Force) }
``` 
### `Import-Module`
Import `SmbShare` module
```powershell
Import-Module SmbShare
```
### `Install-Module`
Install the `Az` module
```powershell
Install-Module -Name Az -AllowClobber
```
### `Install-WindowsFeature`
Install Windows features and roles [[^][Zacker]: 15-16]

Option  | Description
---     | ---
`-IncludeAllSubFeature`
`-IncludeManagementTools`

Install a feature
```powershell
Install-WindowsFeature -Name $featurename -IncludeAllSubFeature -IncludeManagementTools
```
Install Remote Server Adminstration Tools for PowerShell
```powershell
Install-WindowsFeature -Name RSAT-ADDS -IncludeAllSubFeature
```
Install Hyper-V
```powershell
Install-WindowsFeature -Name Hyper-V -IncludeAllSubFeature -IncludeManagementTools -Restart
```
Install Web Server
```powershell
Install-WindowsFeature Web-Server,Web-Common-Http,Web-Mgmt-Console -Restart
```
Create a domain controller
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Import-Module ADDSDeployment
```
### `Invoke-Command`
Execute the commands in the block on the machines specified
```powershell
Invoke-Command -ComputerName core01,core02 -Scriptblock {ipconfig /all}
```
### `Invoke-WebRequest`
Download a file over HTTP/HTTPS
```powershell
Invoke-WebRequest -Uri http://example.com/path/to/file -OutFile \\path\to\local\file
```
Resume a partial download
```powershell
Invoke-WebRequest -Uri http://example.com/path/to/file -Resume -Outfile \\path\to\local\file
```
Transfer a file over FTP/SFTP
```powershell
Invoke-WebRequest ftp://ftp.example.com/file -Outfile C:\path\to\file -Credential ftpuseraccount
```
Resolve shortened URLs
```powershell
$Uri = 'short-url/extension' 
$Web = Invoke-WebRequest -Uri 
$Uri -UseBasicParsing  $Web.BaseResponse.ResponseUri.AbsoluteUri
```
Scrape links from a website
```powershell
(Invoke-WebRequest -Uri "https://techrepublic.com").Links.Href
```
Request data from a website impersonating a browser
```powershell
Invoke-WebRequest -Uri http://microsoft.com -UserAgent ([Microsoft.PowerShell.Commands.PSUserAgent]::Chrome)
```
### `New-Alias`
Establish a new alias
```powershell
New-Alias ip Get-NetIPAddress
```
### `New-Guid`
Generate a GUID
```powershell
New-Guid
(New-Guid).Guid | clip
```
### `New-NetFirewallRule`
Set a new firewall rule for incoming WinRM connections
```powershell
New-NetFirewallRule -DisplayName "WinRMHTTP" -Direction Inbound -LocalPort 5985 -Protocol TCP -Action Allow
```
### `New-NetIpAddress`
Manually configure network interface, if a DHCP server is unavailable [[^][Zacker]: 19]

Option  | Description
---     | ---
`DefaultGateway` | Specifies IP address of local router that computer should use to access other networks
`InterfaceIndex` | Identifies adapter to be configured using interface numbers as displayed by [`Get-NetAdapter`](#get-netadapter)
`IpAddress` | Specifies IP address to be assigned to adapter
`PrefixLength` | Specifies subnet mask value

Configure a network adapter 
```powershell
New-NetIpAddress -InterfaceIndex 6 -IpAddress 192.168.0.200 -PrefixLength 24 -DefaultGateway 192.168.0.1
```
### `New-Partition`
Use all available size for a new partition [^][16]
```powershell
New-Partition -DiskNumber 1 -UseMaximumSize
```
Automatically assign a drive letter
```powershell
New-Partition -DiskNumber 1 -UseMaximumSize -AssignDriveLetter
```
### `New-PSSession`
Option  | Description
---     | ---
`-ComputerName`

Manage a Windows Server remotely [[^][Zacker]: 21]
```powershell
New-PSSession -ComputerName rtmsvrd
```
Start a new PowerShell session, connecting to the specified computer
```powershell
New-PSSession -ComputerName core02
```
### `New-VMSwitch`
Turn on NAT on the nested Hyper-V VM
```powershell
New-VMSwitch -name VMNAT -SwitchType Internal
New-NetNAT -Name LocalNAT -InternalIPInterfaceAddressPrefix "192.168.100.0/24"
```
### `Out-Null`
### `Remove-Partition`
Remove a partition [^][16]
```powershell
Remove-Partition -DiskNumber 1 -PartitionNumber 1
```
Remove a partition without confirmation
```powershell
Remove-Partition -DiskNumber 1 -PartitionNumber 1 -Confirm:$false
```
### `Set-Alias`
Edit an existing alias
```powershell
Set-Alias ip Get-NetAdapter
```
### `Set-Clipboard`
Copy text to clipboard
```powershell
Write-Output 'Hello' | Set-Clipboard
```
With `Append` switch parameter, items can be added without clearing the clipboard:
```powershell
Write-Output 'Hello' | Set-Clipboard -Append
```
### `Set-DnsClientServerAddress`
Configure DNS server addresses [[^][Zacker]: 20]

Option  | Description
---     | ---
`-InterfaceIndex`
`-ServerAddresses`

Configure DNS server addresses [[^][Zacker]: 20]
```powershell
Set-DnsClientServerAddress -InterfaceIndex 6 -ServerAddresses ("192.168.0.1", "192.168.0.2")
```
### `Set-ExecutionPolicy`
### `Set-Location`
### `Set-NetFirewallRule`
Set firewall rule for COM+ Network Access (DCOM-In)
```powershell
Set-NetFirewallRule -name COMPlusNetworkAccess-DCOM-In -Enabled True
```
Set firewall rule for Remote Event Log Management (NP-In)
```powershell
Set-NetFirewallRule -name RemoteEventLogSvc-In-TCP -Enabled True
```
Set firewall rule for Remote Event Log Management (RPC)
```powershell
Set-NetFirewallRule -name RemoteEventLogSvc-NP-In-TCP -Enabled True
```
Set firewall rule for Remote Event Log Management (RPC-EPMAP)
```powershell
Set-NetFirewallRule -name RemoteEventLogSvc-RPCSS-TCP -Enabled True
```
### `Set-PSReadlineOption`
Set history to only save unique commands
```powershell
Set-PSReadlineOption -HistoryNoDuplicates:$true
```
Enable bash-like ambiguous command completion, where tab brings up a menu of matches
```powershell
Set-PSReadlineOption -EditMode Emacs
```
Change `<Tab>` behavior back to default for PowerShell
```powershell
Set-PSReadlineOption -EditMode Windows
```
### `Set-VMMemory`
Disable dynamic memory on a virtual host (nested virtualization)
```powershell
Set-VMMemory -VMName SRV01 -DynamicMemoryEnabled $false
```
### `Set-VMNetworkAdapter`
Turn on MAC address spoofing on a virtual host (nested virtualization)
```powershell
Set-VMNetworkAdapter -VMName SVR01 -Name "NetworkAdapter" -MACAddressSpoofing On
```
### `Set-VMProcessor`
Configure 2 virtual processors on a virtual host (nested virtualization)
```powershell
Set-VMProcessor -VMName SVR01 -Count 2
```
### `Start-Service`
Start the `WinRM` service
```powershell
Start-Service WinRM
```
```powershell
sasv winrm
```
### `Stop-Service`
Stop the `WinRM` service
```powershell
Stop-Service WinRM
```
```powershell
spsv winrm
```
### `Update-Help`
Download help files
### `Write-Output`
Copy text to clipboard
```powershell
Write-Output 'Hello' | Set-Clipboard
```
### `Install-ADDSForest`
Add a new forest
```powershell
# This will prompt for safe mode administrator password
Install-ADDSForest -DomainName example.com -InstallDNS
```
If the system fails to automatically create a NetBIOS name, it can be manually specified with the named parameter `-DomainNetbiosName`
### `Get-ADForest`
Display installed forests
```powershell
Get-ADForest | select -ExpandProperty domains
```
### `Install-ADDSDomain`
Add a new domain
`Install-ADDSDomain` only requires the following two parameters:
  - `-NewDomainName` if the value set for `-DomainType` is set to `ChildDomain` (which it is by default), a single label domain name can be used.
  - `ParentDomainName` the name of an existing parent domain
```powershell
Install-ADDSDomain -NewDomainName hq -ParentDomainName pythagoras.net
```
```powershell
Install-ADDSDomain -Credential (Get-Credential CORP\EnterpriseAdmin1) -NewDomainName child -ParentDomainName corp.contoso.com -InstallDNS -CreateDNSDelegation -DomainMode Win2003 -ReplicationSourceDC DC1.corp.contoso.com -SiteName Houston -DatabasePath "D:\NTDS" -SYSVOLPath "D:\SYSVOL" -LogPath "E:\Logs" -NoRebootOnCompletion
```
### `Uninstall-ADDSDomainController`
Demote a domain controller (consummate with uninstalling the AD Domain Controller role)
```powershell
# When removing the last domain controller of a domain, additional options need to be specified that result in the obliteration of the domain, its forest, and associated data.
Uninstall-ADDSDomainController -LocalAdministratorPassword (ConvertTo-SecureString $pw -AsPlainText -Force) -LastDomainControllerInDomain -RemoveApplicationPartitions
```
### `New-ADComputer`
### `New-ADUser`
Create a new user (disabled by default)
```powershell
New-ADUser -Name "Walter Mitty"

# Users are disabled by default, so you must enable them by setting the `-Enabled` switch parameter:
New-ADUser -Name "Marty McFly" -Enabled $true -GivenName "Martin" -Surname "McFly" -AccountPassword ( ConvertTo-SecureString "P@ssw0rd!" -AsPlainText -Force) 
```
### `Unlock-ADAccount`
Unlock account
```powershell
Unlock-ADAccount -identity wbryan
```
### `Set-ADAccountPassword`
Reset password
```powershell
Set-ADAccountPassword -Identity MBentley -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "What is 255.255.255.240" -Force`)
```
### `New-ADOrganizationalUnit`
Create a new Organizational Unit
```powershell
New-ADOrganizationalUnit -Name GNV -Credential officeprodemoco\joey
```
### `Set-ADOrganizationalUnit`
Remove accidental deletion protection
```powershell
Set-ADOrganizationalUnit -Name GNV -ProtectedFromAccidentalDeletion $False -Identity "OU=GNV, DC=officeprodemoco, DC=onmicrosoft, DC=com" 
```
### `Remove-ADOrganizationalUnit`
Remove an OU
```powershell
Remove-ADOrganizationalUnit -Identity "OU=GNV, DC=officeprodemoco, DC=onmicrosoft, DC=com" -confirm:$False
```
### `Get-ADOrganizationalUnit`
Display OUs, confirming deletion has taken place
```powershell
Get-ADOrganizationalUnit  -filter * | ft
```
### `Get-ADUser`
Display information for Active Directory user `mike`
```powershell
Get-ADUser -Identity mike
```
Display Protection from Accidental Deletion
```powershell
Get-ADUser -Filter *  -Properties ProtectedFromAccidentalDeletion
  -SearchBase "OU=RoadCrew,OU=office365,DC=officeprodemoco,DC=com,DC=onmicrosoft"  `
```
Display information on user, confirming successful creation
```powershell
Get-ADUser "Marty McFly" | Select-Object Name
```
### `Set-ADObject`
Protect users in a specified OU from accidental deletion
```powershell
Get-ADUser -Filter * -SearchBase "OU=RoadCrew,OU=office365,DC=officeprodemoco,DC=com" ` | 
Set-ADObject -ProtectedFromAccidentalDeletion $true
```
### `Set-VMFirmware`
Enable secure boot on Generation 2 Linux VMs [^][IMWS]
```powershell
Set-VMFirmware vmname -SecureBootTemplate MicrosoftUEFICertificateAuthority
```
### `Search-ADAccount`

Option                        | Effect
:---                          | :---
`-AccountDisabled`            | filter disabled accounts
`-AccountExpired`             | filter expired accounts
`-ComputersOnly`              | filter computer accounts
`-LockedOut`                  | filter locked out accounts
`-PasswordExpired`            | filter accounts with expired passwords
`-PasswordNeverExpires`       | filter accounts with passwords that will never expire
`-UsersOnly`                  | filter users

Display accounts that have been inactive for the last 90 days
```powershell
Search-ADAccount -AccountInactive -TimeSpan 90.00:00:00
```
Display accounts expiring on a particular date
```powershell
Search-ADAccount -AccountExpiring -DateTime "3/18/2019"
``` 
### `Start-DscConfiguration`
Used to erect a **push architecture** in [DSC](dsc.md). [[^][Zacker]: 27]

Option  | Description
---     | ---
`-Path`

## Sources
[3]: ../sources/az-103.md "Michael Washam, Jonathan Tuliani, and Scott Hoag. _Exam Ref AZ-103 Microsoft Azure Administrator_."
[4]: https://www.techrepublic.com/article/how-to-use-wget-to-download-web-based-packages-on-windows/#ftag=RSS56d97e7 "techrepublic.com - How to use Wget to download web-based packages on Windows."
[5]: http://www.powertheshell.com/topic/learnpowershell/firststeps/psversion/ "powertheshell.com - Check PowerShell Version"
[6]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-6 "Microsoft Docs - About Comparison Operators"
[7]: https://mathieubuisson.github.io/powershell-linux-bash/ "mathieubuisson.github.io - PowerShell equivalents for common Linux/bash commands"
[8]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6 "Microsoft Docs - About Functions"
[9]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/select-object?view=powershell-6 "Microsoft Docs - Select-Object"
[10]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-6 "Microsoft Docs - About CommonParameters"
[11]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-6 "Microsoft Docs - About Parameters Default Values"
[12]: https://mikefrobbins.com/2019/08/01/whats-in-your-powershell-psdefaultparametervalues-preference-variable/ "mikefrobbins.com - What's in your PowerShell `$PSDefaultParameterValues` Preference Variable?"
[13]: https://adamtheautomator.com/powershell-copy-to-clipboard/ "adamtheautomater.com - Using PowerShell to Copy to the Clipboard"
[14]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-6 "Microsoft Docs - About Automatic Variables"
[15]: https://ridicurious.com/2019/07/29/3-ways-to-unzip-compressed-files-using-powershell/ "ridicurious.com - 3 ways to unzip compressed files using PowerShell"
[16]: https://sumtips.com/tips-n-tricks/manage-disk-partitions-with-windows-powershell/ "SumTips.com - Manage disk partitions with Windows PowerShell"

[ADAC]: ../sources/adac.md "Berkouwer, Sander. _Active Directory Administration Cookbook_."
[WSAC]: ../sources/wsac.md "Krause, Jordan. _Windows Server 2016 Administration Cookbook_."
[IMWS]: ../sources/imws.md "McCabe, John. _Introduction to Microsoft Windows Server 2016_."
[Zacker]: ../certs/70-740.md "Zacker, Craig. _Installation, Storage and Compute with Windows Server 2016: Exam Ref 70-740_. 2017."

[Add-Computer]: ../win/pwsh.md#add-computer "Join a computer to a domain"
[Add-PSSnapin]: ../win/pwsh.md#add-pssnapin "Load a given list of snap-ins (.NET assemblies containing a collection of cmdlets and/or providers for use within PowerShell) either by name or via the pipeline - last supported in PowerShell 5.1"
[Disconnect-PSSession]: ../win/pwsh.md#disconnect-pssession "Terminate a remote PowerShell session begun with `New-PSSession`"
[Enable-PSRemoting]: ../win/pwsh.md#enable-psremoting "Allow remote PowerShell management"
[Enter-PSSession]: ../win/pwsh.md#enter-pssession "Interact with the specified PowerShell session"
[Expand-Archive]: ../win/pwsh.md#expand-archive "Decompress archives"
[Export-CliXml]: ../win/pwsh.md#export-clixml "Serialize a PowerShell object as a Common Language Infrastructure (CLI) XML file"
[Export-Csv]: ../win/pwsh.md#export-csv "Export PowerShell objects to CSV"
[ForEach-Object]: ../win/pwsh.md#filters "(alias: %)"
[Format-List]: ../win/pwsh.md#output-formatting "Display output in list style (alias: fl)"
[Format-Table]: ../win/pwsh.md#output-formatting "Display output in table style (alias: ft)"
[Get-Alias]: ../win/pwsh.md#get-alias "Display aliases"
[Get-ChildItem]: ../win/pwsh.md#get-childitem "Get items in one or more locations"
[Get-Clipboard]: ../win/pwsh.md#get-clipboard "Display items in clipboard"
[Get-Command]: ../win/pwsh.md#get-command "Display all installed commands, including aliases, applications, filters, functions, and scripts (alias: gcm)"
[Get-Help]: ../win/pwsh.md#get-help "Display help file for cmdlets"
[Get-History]: ../win/pwsh.md#get-history "Display history of inputted commands for the current session"
[Get-Member]: ../win/pwsh.md#get-member "Display properties and methods of a PowerShell object (alias: gm)"
[Get-Module]: ../win/pwsh.md#get-module "Display currently loaded PowerShell modules"
[Get-NetAdapter]: ../win/pwsh.md#get-netadapter "Display available network interfaces"
[Get-PSDrive]: ../win/pwsh.md#get-psdrive "Display mapped drives"
[Get-PSSnapin]: ../win/pwsh.md#get-pssnapin "Display currently loaded snapins (.NET assemblies containing a collection of cmdlets and/or providers for use within PowerShell) - last supported in PowerShell 5.1"
[Get-Process]: ../win/pwsh.md#get-process "Display running processes"
[Get-Service]: ../win/pwsh.md#get-service "Display services (alias: gsv)"
[Import-CliXml]: ../win/pwsh.md#import-clixml "Import a Common Language Infrastructure (CLI) XML file with data that represents Microsoft .NET Framework objects and create PowerShell objects from it"
[Import-Csv]: ../win/pwsh.md#import-csv "Import CSV files as PowerShell objects"
[Import-Module]: ../win/pwsh.md#import-module "Manually import a module, rather than waiting for it to load dynamically when using one of its cmdlets (alias: ipmo)"
[Install-WindowsFeature]: ../win/pwsh.md#install-windowsfeature "Install Windows features and roles"
[New-NetIpAddress]: ../win/pwsh.md#new-netipaddress "Manually configure network interface, if a DHCP server is unavailable"
[New-PSSession]: ../win/pwsh.md#new-pssession "Start a new remote PowerShell session with a remote computer"
[New-VMSwitch]: ../win/pwsh.md#new-vmswitch " "
[Out-Null]: ../win/pwsh.md#out-null "Dispose of information piped to it, in lieu of displaying it"
[Select-Object]: ../win/pwsh.md#filters "(alias: select)"
[Set-DnsClientServerAddress]: ../win/pwsh.md#set-dnsclientserveraddress "Configure DNS server addresses"
[Set-ExecutionPolicy]: ../win/pwsh.md#set-executionpolicy "Change PowerShell execution policy for Windows computers (Windows only)"
[Set-Location]: ../win/pwsh.md#set-location "Set present working directory (alias: cd)"
[Set-VMFirmware]: ../win/pwsh.md#set-vmfirmware " "
[Start-DscConfiguration]: ../win/pwsh.md#start-dscconfiguration "Erect a push architecture in DSC"
[Start-Service]: ../win/pwsh.md#start-service " "
[Stop-Service]: ../win/pwsh.md#stop-service " "
[Update-Help]: ../win/pwsh.md#update-help "Download help files"
[Where-Object]: ../win/pwsh.md#filters "(alias: ?)"
[Write-Output]: ../win/pwsh.md#write-output " "