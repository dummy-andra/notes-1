# Windows Server and Active Directory

Term                                              | Definition | Source
---                                               | ---        | ---
Active Server Pages (ASP)                         | Microsoft scripting technology
Active Directory Federation Services (AD FS)      | used by the __Web Application Proxy__ role service of __Remote Access__ role to authenticate corporate users to allow access to intranet web applications from the outside | [WSAF](sources/wsaf.md): 158
DirectAccess                                      | Allows access to corporate intranet without using a VPN. Introduced in Windows Server 2008 R2; uses __IPsec__ protocol to encrypt communication between client and server; encapsulave IPv6 traffic over IPv4 to reach intranet from the internet. | [WSAF](sources/wsaf.md): 157
Distributed Component Object Model (DCOM)         | Microsoft technology for communication between software components on networked computers which provides the communication infrastructure for __Microsoft COM+__ application servers.| [ITP](sources/itp-winsrv-mcsa.md)
domain                                            | an administrative boundary for Active Directory (usually symbolized by a triangle)
forest                                            | security boundary for Active Directory
functional level                                  | determines available AD DS capabilities at the Forest and Domain levels | [WSAF](sources/wsaf.md): 117
group                                             | collection of Active Directory objects, typically representing users, computers, peripheral devices, and network services | [WSAF](sources/wsaf.md): 182
Group Policy Object (GPO)                         | collection of configured parameters that show how computers will looka nd behave for a certain group of users | [WSAF](sources/wsaf.md): 183
Internet Client Printing (ICP)                    | technology used for the __Internet Printing__ role service of the __Print and Document Services__ role
IPsec                                             | Secure protocol used by __DirectAccess__ | [WSAF](sources/wsaf.md): 157
Network Operating System (NOS)                    | software capable of managing, maintaining, and providing resources in the network | [WSAF](sources/wsaf.md): 14
Remote Desktop Connection (RDC)                   |  | [WSAF](sources/wsaf.md): 163
Remote Procedure Call (RPC)                       | protocol that one program can use to request a service from a program located on another network host without having to navigate that network | [ITP](sources/itp-winsrv-mcsa.md)
Virtual Private Network (VPN)                     | secure path within a organization's network, or on the internet, for transmitting sensitive data | [WSAF](sources/wsaf.md): 164


Program                                           | Binary        | Description   |Source
---                                               | ---           | ---           | ---
Active Directory Administrative Center            | dsac.exe      | MMC snap-in used to manage Windows Server directory services | [WSAF](/sources/wsaf.md): 106
Active Directory Users and Computers              | dsa.msc       | MMC snap-in used to manage users, hosts, and relevant information | [WSAF](/sources/wsaf.md): 106
Active Directory Domains and Trusts               | domain.msc    | MMC snap-in used to manage domains, trusts, and relevant information | [WSAF](/sources/wsaf.md): 106
Active Directory Module for Windows PowerShell    |               | MMC snap-in used to manage Active Directory through Powershell cmdlets | [WSAF](/sources/wsaf.md): 106
Active Directory Sites and Services               | dssite.msc    | MMC snap-in used to manage the replication and services between sites | [WSAF](/sources/wsaf.md): 106
Authorization Manager                             | azman.msc     | Used in delegating VM management  | [ITP](sources/itp-winsrv-mcsa.md)
Deployment Image Servicing and Management (DISM)  |               | command-line tool used to mount and service Windows images before deployment, replacing several deployment tools, including __PEimg__, __Intlcfg__, __ImageX__, and __Package Manager__ | [MD](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
Disk Management                                   |               | MMC snap-in corresponding to rule group Remote Volume Management|[ITP](sources/itp-winsrv-mcsa.md)
disk2vhd                                          | disk2vhd      | Make a VHD from a bootable physical drive | [ITP](sources/itp-winsrv-mta.md)
DiskPart                                          |               | manage drives, including disks, partitions, volumes, and virtual hard disks |  | [MD](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart)
Event Viewer                                      |               | MMC snap-in corresponding to rule group Remote Event Log Management|[ITP](sources/itp-winsrv-mcsa.md)
Fsutil                                            | fsutil.exe    | Performs tasks that are related to file allocation table (FAT) and NTFS file systems, such as managing reparse points, managing sparse files, or dismounting a volume           | [MD](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/fsutil)
Group Policy Management Console (GPMC)            | gpmc.msc      | Manage GPOs | [WSAF](sources/wsaf.md): 184
ImageX                                            |               | command-line tool that allows an admin to image an entire hard drive in WIM format
Internet Information Services (IIS)               |               | Console used to manage web servers  | [ITP](sources/itp-winsrv-mta.md)
Local Users and Groups                            | lusrmgr.msc   | Used to add users to the Hyper-V Administrators container  | [ITP](sources/itp-winsrv-mcsa.md)
Local Group Policy Editor                         | gpedit.msc    | Used to assign user permissions | [WSAF](sources/wsaf.md): 175, 187
Microsoft Management Console (MMC)                |               | Component of Windows that hosts __snap-ins__, allowing multiple management tools to be accessed from the same interface. An example component is __Computer Management__.|[ITP](sources/itp-winsrv-mcsa.md)
ntdsutil                                          | ntdsutil.exe  | older command-line utility that provides access to a variety of Active Directory functions | 
Server Manager                                    |               | A GUI-based tool for managing servers, introduced in Windows Server 2008. __Scope Pane__ shows installed roles, __Details Pane__ displays details of a selected role. | [WSAF](sources/wsaf.md): 144
Services                                          |               | MMC snap-in corresponding to rule group Remote Service Management| [ITP](sources/itp-winsrv-mcsa.md)
Shared Folders                                    |               | MMC snap-in corresponding to rule group File and Printer Sharing| [ITP](sources/itp-winsrv-mcsa.md)
Task Scheduler                                    |               | MMC snap-in corresponding to rule group Performance Logs and Alerts, File and Printer Sharing | [ITP](sources/itp-winsrv-mcsa.md)
Windows Defender Firewall with Advanced Security  | wf.msc        |               | [ITP](sources/itp-winsrv-mcsa.md)
Windows Firewall and Advanced Security            |               | MMC snap-in corresponding to rule group Windows Firewall Remote Management | [ITP](sources/itp-winsrv-mcsa.md)
Windows Remote Shell (WinRS)                      |               |               | [ITP](sources/itp-winsrv-mcsa.md)
Windows Remote Management (WinRM)                 | winrm.exe     | Microsoft's implementation of the __WS-Management Protocol__. Unlike MMCs, which are based on DCOM (legacy technology), WinRM is considered firewall-friendly and is the preferred option, especially since its `quickconfig` makes setting up remote management easier | [ITP](sources/itp-winsrv-mcsa.md)

File                                        | Description | Source
---                                         | ---         | ---
C:\Windows\NTDS\ntds.dit                    | Active Directory database; divided up into partitions for __Schema__, __Configuration__, and __Domain__ | [ITP](sources/itp-winsrv-mta.md)
C:\Windows\SYSVOL\sysvol\<domain>\Policies  | where Group Policy information is stored | [ITP](sources/itp-winsrv-mta.md), [WSAF](sources/wsaf.md): 182


A __role__ is the primary task assigned to a server. You add them to a server using __Server Manager__ through the __Add Roles and Features__ wizard, and they come at no additional cost.  __Role Services__ augment the functionality of installed roles. __Features__ are also available from within the __Add Roles and Features__ wizard

Windows Server role or feature       | Description       | Role Services | Source
---                                  |  ---              | ---           | ---
Active Directory Users and Computers | N/A               | N/A           | [ITP](sources/itp-winsrv-mta.md)
DNS Server                           | N/A               | N/A           | [ITP](sources/itp-winsrv-mta.md)
File Services                        | Automatically added upon completing the installation of WS2016 | N/A | [WSAF](sources/wsaf.md): 166
Print and Document Services          | Network printers  | __Print Server__ (manage print queues and deployment and migration of print servers), __Distributed scan server__ (configure, manage, and administer scanners and scanned documents), __Internet printing__ (set up a website where users can print using ICP), __LPD Service__ (allow Unix-based computer to use `lpr` to print)  | [ITP](sources/itp-winsrv-mta.md), [WSAF](sources/wsaf.md): 167-172
Remote Access                        | Enables remote access to resources within an intranet | __DirectAccess and VPN (RAS)__; __Routing and Remote Access Service (RRAS)__; __Web Application Proxy__ | [WSAF](sources/wsaf.md): 157-8, 164
Remote Assistance                    | Enable a helper to access the host's desktop remotely for the purpose of assisting troubleshooting.  | N/A | [WSAF](sources/wsaf.md): 159
Remote Desktop Services (RDS)        | Known as __Terminal Services__ until 2008 | __Remote Desktop Gateway (RDG)__  enables authorized users to connect to computers within an organization's network and over the internet using a Remote Desktop Connection (RDC); __Remote Desktop Connection Broker__ allows users to reconnect to existing virtual desktop, RemoteApp programs, and session-based desktops, even load distribution across RD Session Host servers in a session collection or across pooled virtual desktops in a pooled virtual desktop collection, and access virtual desktops in a virtual desktop collection   | [WSAF](sources/wsaf.md): 162
Remote Server Administration Tools (RSAT) | One of the ways to remotely administer a domain controller |  | [ITP](sources/itp-winsrv-mcsa.md)
Web Server (IIS)                     | Supports communication protocols such as HTTP, HTTPS, FTP, FTPS, SMTP, and NNTP for communication between the browser and the web server, including ASP. | FTP Server (FTP Service, FTP Extensibility) | [WSAF](sources/wsaf.md): 152

__Application servers__ are individual Microsoft products that require their own licenses.

Application Servers   | Product               | Description
---                   | ---                   | ---
Mail server           | Exchange Server       | Protocols: POP3, IMAP, SMTP
Database server       | Microsoft SQL Server  | Protocols: Open Database Connectivity (ODBC), Java Database Connectivity (JDBC), Object Linking and Embedding Database (OLEDB)
Collaboration server  | Sharepoint Server     | 
Monitoring server     | System Center Operations MAnager (SCOM) | Deploy, configure, manage, and monitor operations, services, devices, and applications of enterprise systems through a single console
Threat management     | System Center 2016 Endpoint Protection, also Forefront Threat Management Gateway (Forefront TMG), foremerly Microsoft Internet Security and Acceleration (ISA) Server; network router, firewall, VPN server, and web cache

## NTFS

NTFS permission | Description 
---             | ---
Full control    | allow reading, writing, modifying, executing, changing attributes and permissions, and deleting files and subfolders 
Modify          | reading, modifying, adding, and deleting files and subfolders
List folder contents  | viewing data files and list of folder's content
Read | viewing file and file properties
Read and Execute| running and executing files
Write
Special permissions

Share permissions
  - Full control
  - Change
  - Read
