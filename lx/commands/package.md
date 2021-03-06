[https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/]: https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/ "Fedora Docs: \"Getting started with virtualization\""

[add-apt-repository]:                                package.md#add-apt-repository                      '```&#10;$ add-apt-repository&#10;```&#10;'
[apt]:                                               package.md#apt                                     '```&#10;$ apt&#10;```&#10;'
[apt-cache]:                                         package.md#apt-cache                               '```&#10;$ apt-cache&#10;```&#10;Display package information regarding the package cache&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 81'
[apt-cache]:                                         package.md#apt-cache                               '```&#10;$ apt-cache&#10;```&#10;'
[apt-get]:                                           package.md#apt-get                                 '```&#10;$ apt-get&#10;```&#10;'
[dnf]:                                               package.md#dnf                                     '```&#10;$ dnf&#10;```&#10;Package manager for Red Hat systems that supercedes `yum`&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 86'
[dpkg]:                                              package.md#dpkg                                    '```&#10;$ dpkg&#10;```&#10;Manage local Debian packages&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 79'
[dpkg-reconfigure]:                                  package.md#dpkg-reconfigure                        '```&#10;$ dpkg-reconfigure&#10;```&#10;Run the configuration script again for a package that has already been installed.&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 80'
[gem]:                                               package.md#gem                                     '```&#10;$ gem&#10;```&#10;'
[pacman]:                                            package.md#pacman                                  '```&#10;$ pacman&#10;```&#10;'
[pip]:                                               package.md#pip                                     '```&#10;$ pip&#10;```&#10;'
[rpm]:                                               package.md#rpm                                     '```&#10;$ rpm&#10;```&#10;Install, upgrade, and remove .rpm packages&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 78'
[snap]:                                              package.md#snap                                    '```&#10;$ snap&#10;```&#10;'
[yay]:                                               package.md#yay                                     '```&#10;$ yay&#10;```&#10;'
[yum]:                                               package.md#yum                                     '```&#10;$ yum&#10;```&#10;Package manager for Red Hat systems&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 83'
[yumdownloader]:                                     package.md#yumdownloader                           '```&#10;$ yumdownloader&#10;```&#10;Download software packages without installing them&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 84'
[zypper]:                                            package.md#zypper                                  '```&#10;$ zypper&#10;```&#10;Package manager for SUSE with a syntax similar to that of `yum`&#10;Rothwell, William. _CompTIA Linux+ Portable Command Guide_.: 86'

<!-- `dpkg` options -->
[dpkg -&#67;]:                                        #dpkg                                              '```&#10;$ dpkg -C&#10;$ dpkg --audit&#10;```&#10;Check for broken packages'
[dpkg -&#69;]:                                        #dpkg                                              '```&#10;$ dpkg -E&#10;```&#10;Do not overwrite a previously installed package of the same version&#10;: 47'
[dpkg -&#71;]:                                        #dpkg                                              '```&#10;$ dpkg -G&#10;```&#10;Do not overwrite a previously installed package with an older version of that same package&#10;: 47'
[dpkg -&#105;]:                                       #dpkg                                              '```&#10;$ dpkg -i $PACKAGE&#10;$ dpkg --install $PACKAGE&#10;```&#10;Install `$PACKAGE`&#10;: 48'
[dpkg -&#73;]:                                        #dpkg                                              '```&#10;$ dpkg -I $PACKAGE&#10;$ dpkg --info $PACKAGE&#10;```&#10;Show information about `$PACKAGE`'
[dpkg -&#108;]:                                       #dpkg                                              '```&#10;$ dpkg -l $PATTERN&#10;$ dpkg --list $PATTERN&#10;```&#10;Display information for installed package names that match `$PATTERN`&#10;: 48'
[dpkg -&#76;]:                                        #dpkg                                              '```&#10;$ dpkg -L $PACKAGE&#10;$ dpkg --listfiles $PACKAGE&#10;```&#10;List files installed from `$PACKAGE`&#10;: 48'
[dpkg -&#80;]:                                        #dpkg                                              '```&#10;$ dpkg -P $PACKAGE&#10;$ dpkg --purge $PACKAGE&#10;```&#10;Remove everything for `$PACKAGE`&#10;: 48'
[dpkg -&#112;]:                                       #dpkg                                              '```&#10;$ dpkg -p $PACKAGE&#10;$ dpkg --print-avail $PACKAGE&#10;```&#10;Show details about `$PACKAGE`'
[dpkg -&#82;]:                                        #dpkg                                              '```&#10;$ dpkg -R&#10;$ dpkg --recursive&#10;```&#10;Recursively process package files in specified subdirectories&#10;: 48'
[dpkg -&#114;]:                                       #dpkg                                              '```&#10;$ dpkg -r $PACKAGE&#10;$ dpkg --remove $PACKAGE&#10;```&#10;Remove everything except configuration files for `$PACKAGE`&#10;: 48'
[dpkg -&#115;]:                                       #dpkg                                              '```&#10;$ dpkg -s $PACKAGE&#10;$ dpkg --status $PACKAGE&#10;```&#10;Report the status of `$PACKAGE`&#10;: 48'
[dpkg -&#83;]:                                        #dpkg                                              '```&#10;$ dpkg -S $PATTERN&#10;$ dpkg --search $PATTERN&#10;```&#10;Search for a filename matching `$PATTERN` from installed packages&#10;: 48'
[dpkg --configure]:                                   #dpkg                                              '```&#10;$ dpkg --configure&#10;```&#10;Configure an unpacked package. This involves setup of configuration files&#10;: 48'
[dpkg --print-avail]:                                 #dpkg                                              '```&#10;$ dpkg --print-avail $PACKAGE&#10;```&#10;Display details found in /var/lib/dpkg/available about `$PACKAGE`&#10;: 48'
[dpkg --unpack]:                                      #dpkg                                              '```&#10;$ dpkg --unpack $PACKAGE&#10;```&#10;Unpack `$PACKAGE` but don't install the package it contains&#10;: 48'
[dpkg --get-selections]:                              #dpkg                                              '```&#10;$ dpkg --get-selections&#10;```&#10;Display list of package selections'

<!-- `rpm` options -->
[rpm -&#97;]:                                             #rpm                                               '```&#10;$ rpm -a&#10;$ rpm --all&#10;```&#10;In query mode, display a list of all packages installed on the system&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 55'
[rpm -&#99;]:                                             #rpm                                               '```&#10;$ rpm -c $PACKAGE&#10;$ rpm --configfiles $PACKAGE&#10;```&#10;List only configuration files installed with specified package&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#100;]:                                             #rpm                                               '```&#10;$ rpm -d $PACKAGE&#10;$ rpm --docfiles $PACKAGE&#10;```&#10;List only documentation files installed with specified package&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#101;]:                                             #rpm                                               '```&#10;$ rpm -e $PACKAGE&#10;$ rpm --erase $PACKAGE&#10;```&#10;Remove specified package, including config files&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#102;]:                                             #rpm                                               '```&#10;$ rpm -f $FILENAME&#10;$ rpm --file $FILENAME&#10;```&#10;In query mode, display the package that contains a particular file&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 55'
[rpm -&#104;]:                                             #rpm                                               '```&#10;$ rpm -h&#10;$ rpm --hash&#10;```&#10;Prints a string of 50 hash marks during installation as a progress indicator&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 54'
[rpm -&#105;]:                                             #rpm                                               '```&#10;$ rpm -i $PACKAGE&#10;$ rpm --install $PACKAGE&#10;```&#10;Install specified packages&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#73;]:                                             #rpm                                               '```&#10;$ rpm -I $PACKAGE&#10;```&#10;Display information about specified package&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#75;]:                                             #rpm                                               '```&#10;$ rpm -K $PACKAGE&#10;```&#10;Verify integrity of specified package'
[rpm -&#108;]:                                             #rpm                                               '```&#10;$ rpm -l $PACKAGE&#10;$ rpm --list $PACKAGE&#10;```&#10;List all files installed with specified package&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#112;]:                                             #rpm                                               '```&#10;$ rpm -p $FILENAME&#10;```&#10;Query a package file (most useful with `-i`)&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.'
[rpm -&#113;]:                                             #rpm                                               '```&#10;$ rpm -q $PACKAGE&#10;$ rpm --query $PACKAGE&#10;```&#10;Query for specified package'
[rpm -&#82;]:                                             #rpm                                               '```&#10;$ rpm -R $PACKAGE&#10;$ rpm --requires $PACKAGE&#10;```&#10;List packages on which this package depends&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 56'
[rpm -&#115;]:                                             #rpm                                               '```&#10;$ rpm -s&#10;```&#10;Display the state of each file that was installed by the specified package (`normal`, `not installed`, or `replaced`)'
[rpm -&#85;]:                                             #rpm                                               '```&#10;$ rpm -U $PACKAGE&#10;$ rpm --upgrade $PACKAGE&#10;```&#10;Upgrade specified package'
[rpm -&#118;]:                                             #rpm                                               '```&#10;$ rpm -v&#10;```&#10;Verbose output&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 54'
[rpm -&#86;]:                                             #rpm                                               '```&#10;$ rpm -V&#10;$ rpm --verify&#10;```&#10;Compare files from installed packages against their expected configuration from the RPM database.&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 58'
[rpm --provides]:                                     #rpm                                               '```&#10;$ rpm --provides $PACKAGE&#10;```&#10;List which capabilities the specified package provides'
[rpm --force]:                                        #rpm                                               '```&#10;$ rpm --force&#10;```&#10;Allows the replacement of existing packages and of files from previously installed packages; for upgrades, it allows the replacement of a newer package with an older one.&#10;Equivalent to using all of the following options:&#10;  `--replacepkgs`&#10;  `--replacefiles`&#10;  `--oldpackage`&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 54'
[rpm --nodeps]:                                       #rpm                                               '```&#10;$ rpm --nodeps&#10;```&#10;Allows you to install a package without checking for dependencies.&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 54'
[rpm --test]:                                         #rpm                                               '```&#10;$ rpm --test&#10;```&#10;Runs through all the motions except for actually writing files; useful to verify that a package will install correctly prior to making the attempt&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 54'
[rpm --nofiles]:                                      #rpm                                               '```&#10;$ rpm --nofiles&#10;```&#10;In verify mode, ignore missing files&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 58'
[rpm --nomd5]:                                        #rpm                                               '```&#10;$ rpm --nomd5&#10;```&#10;In verify mode, ignore MD5 checksum errors&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 58'
[rpm --nopgp]:                                        #rpm                                               '```&#10;$ rpm --nopgp&#10;```&#10;In verify mode, ignore PGP checking errors&#10;Haeder, Adam. _LPI Linux Certification in a Nutshell_. 2010.: 58'

# Linux package management commands

&nbsp;  | Commands
---     | ---
&nbsp;  | [`add-apt-repository`][add-apt-repository] [`apt`][apt] [`apt-cache`][apt-cache] [`apt-get`][apt-get] [`dnf`][dnf] [`dpkg`][dpkg] [`dpkg-reconfigure`][dpkg-reconfigure] [`gem`][gem] [`pacman`][pacman] [`pip`][pip] [`rpm`][rpm] [`snap`][snap] [`yay`][yay] [`yum`][yum] [`yumdownloader`][yumdownloader] [`zypper`][zypper] 

Commands    | Options
---         | ---
[`dpkg`][dpkg] | <code>&nbsp;</code>  <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`i`][dpkg -&#105;] <code>&nbsp;</code> <code>&nbsp;</code> [`l`][dpkg -&#108;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`p`][dpkg -&#112;] <code>&nbsp;</code> [`r`][dpkg -&#114;] [`s`][dpkg -&#115;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code>  <br><code>&nbsp;</code>&nbsp;<code>&nbsp;</code> <code>&nbsp;</code> [`C`][dpkg -&#67;] <code>&nbsp;</code> [`E`][dpkg -&#69;] <code>&nbsp;</code> [`G`][dpkg -&#71;] <code>&nbsp;</code> [`I`][dpkg -&#73;] <code>&nbsp;</code> <code>&nbsp;</code> [`L`][dpkg -&#76;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`P`][dpkg -&#80;] <code>&nbsp;</code> [`R`][dpkg -&#82;] [`S`][dpkg -&#83;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> 
[`rpm`][rpm] | <code>&nbsp;</code>  [`a`][rpm -&#97;] <code>&nbsp;</code> [`c`][rpm -&#99;] [`d`][rpm -&#100;] [`e`][rpm -&#101;] [`f`][rpm -&#102;] <code>&nbsp;</code> [`h`][rpm -&#104;] [`i`][rpm -&#105;] <code>&nbsp;</code> <code>&nbsp;</code> [`l`][rpm -&#108;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`p`][rpm -&#112;] [`q`][rpm -&#113;] <code>&nbsp;</code> [`s`][rpm -&#115;] <code>&nbsp;</code> <code>&nbsp;</code> [`v`][rpm -&#118;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code>  <br><code>&nbsp;</code>&nbsp;<code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`I`][rpm -&#73;] <code>&nbsp;</code> [`K`][rpm -&#75;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> [`R`][rpm -&#82;] <code>&nbsp;</code> <code>&nbsp;</code> [`U`][rpm -&#85;] [`V`][rpm -&#86;] <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> <code>&nbsp;</code> 

### `apt`
Upgrade distribution
```sh
apt dist-upgrade
```
Install local {file} as a package
```sh
apt install file
```
Install {package}
```sh
apt install package
```
Search for packages matching {searchexpression}
```sh
apt list pattern
```
Remove {package}
```sh
apt remove package
```
Update package database
```sh
apt update
```
Upgrade all packages
```sh
apt upgrade
```
### `apt-cache`
Display package information regarding package cache

Command   | Description
:---      | :---
`search`  | display all packages with the search term listed in the package name or description
`showpkg` | display information about a package
`stats`   | display statistics about the package cache
`showsrc` | display information about a source package
`depends` | display a package's dependencies
`rdepends`| display a package's reverse dependencies, i.e. what packages for which this package is a dependency

Display basic information about each available package and its dependencies 
```sh
apt-cache dump
```
### `apt-key`
Add a public GPG key to keyring
```sh
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add - # Google Cloud SDK
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -	# Docker
```
### `add-apt-repository`
Add a repository
```sh
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu trusty-security main universe"
```
### `dnf`
View all `dnf` commands
```sh
dnf history
```
View all packages installed by user
```sh
dnf history userinstalled
```
Display information about a **package group** [^][https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/]
```sh
dnf groupinfo virtualization
```
Install a package group [^][https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/]
```sh
dnf install @virtualization
```
Install a package group, including optional packages [^][https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-virtualization/]
```sh
dnf group install --with-optional virtualization
```
### `dpkg`
Manage local Debian packages
### `dpkg-reconfigure`
Run a package's configuration script after it has already been installed.

Change the time zone on a Debian based system using package-based tools
```sh
dpkg-reconfigure tzdata
```
### `gem`
Install a Ruby `$PACKAGE`
```sh
gem install $PACKAGE
```
Display currently installed Ruby packages
```sh
gem list
```
Remove `$PACKAGE`
```sh
gem uninstall package
```
Update `$PACKAGE`
```sh
gem update package
```
### `pacman`
Option  | POSIX option            | Effect
:---    | :---                    | :---
`Q`     | `--query`               | list all installed packages
`-R`    |                         | remove {pkg}, but leave dependencies
`-Qe`   |                         | list programs explicitly installed by user or program command
`-Qeq`  |                         | list only program names explicitly installed
`-Qm`   |                         | list programs only installed from AUR
`-Qn`   |                         | list programs only installed from main repositories
`-Qdt`  |                         | list dependencies no longer needed (orphans)
`-Ql`   | `--query` `--list`      | list all files owned by a package
`-S`    | `--sync`                | install {pkg}
`-Sy`   |                         | synchronize package database 
`-Su`   |                         | update programs 
`-Syu`  |                         | sync package database (`Sy`) and upgrade all programs (`u`) (equivalent to `apt-get update && apt-get upgrade`)
`-Syy`  |                         | force double-check of repositories
`-Syyuw` |                        | downloads programs but doesn't install them, for the option of manual installation
`-Rs`   |                         | remove {pkg} as well as its dependencies
`-Rns`  |                         | remove {pkg}, dependencies, as well as config files 
List installed packages
```sh
pacman -Q
pacman --query
```
List all orphaned dependencies (no longer needed)
```sh
pacman -Qdt
pacman --query --deps --unrequired
```
List only explicitly installed packages and versions
```sh
pacman -Qe
pacman --query --explicit
```
List explicitly installed packages, limiting output to program names
```sh
pacman -Qeq
pacman --query --explicit --quiet
```
List all packages installed from the AUR
```sh
pacman -Qm
pacman --query --foreign
```
List all packages installed from main repos
```sh
pacman -Qn
pacman --query --native
```
Find which package owns {file}
```sh
pacman -Qo file
pacman --query --owns file
```
List all install packages, filtering output to packages that are out-of-date on the local system
```sh
pacman -Qu
pacman --query --upgrades
```
Remove {package}
```sh
pacman -R package
pacman --remove package
```
Remove {package}, dependencies, and config files
```sh
pacman -Rns package
pacman --remove --recursive --nosave
```
Remove {package} as well as its dependencies
```sh
pacman -Rs
pacman --remove --recursive
```
Install {pkg} from the AUR
```sh
pacman -S package
pacman --sync package
```
Remove all packages from the cache as well as unused sync databases
```sh
pacman -Scc
pacman --sync --clean --clean
```
Display information about {package}
```sh
pacman -Si package
pacman --sync --info package
```
Search for {pkg} in AUR repos
```sh
pacman -Ss package
pacman --sync --search package
```
Search for packages matching {searchexpression}
```sh
pacman -Ss pattern
pacman --sync --search pattern
```
Update package database
```sh
pacman -Sy
pacman --sync --refresh
```
Update all packages from AUR and official repos
```sh
pacman -Syu
pacman --sync --refresh --sysupgrade
```
Force refresh of all package databases, even if they appear to be up-to-date
```sh
pacman -Syy
pacman --sync --refresh --refresh
```
Download program updates but don't install them
```sh
pacman -Syyuw
pacman --sync --refresh --refresh --sysupgrade --downloadonly
```
Get number of total installed packages
```sh
pacman -Q | wc -l
```
### `pip`
Display installed packages
```sh
pip list
```
Display information about {package}
```sh
pip show package
```
### `rpm`
Option  | POSIX option            | Effect
:---    | :---                    | :---
`-e`    | `--erase`               | remove specified package, including config files
`-i`    | `--install`             | install specified package
`-q`    | `--query`               | query for specified package
`-U`    | `--upgrade`             | upgrade specified package
`-a`       |                         | list all installed packages
`-c`       |                         | list configs installed with specified package
`-d`       |                         | list documentation files installed with specified package
`-I`       |                         | display information about specified package
`-K`       |                         | Verify integrity of specified package
`-l`       |                         | List all files installed with specified package
`-provides`|                         | List which capabilities the specified package provides
`-R`       |                         | list which capabilities the specified package requires
`-s`       |                         | display state of each file that was installed by specified package (normal, not installed, or replaced)

Query repos for information on {package}
```sh
rpm -qi package
rpm --query --info package
```
Upgrade or install {package}, with progress bars
```sh
rpm -Uvh package
rpm --upgrade --verbose --hash package
```
Display version of Fedora
```sh
rpm -E %fedora
```
### `snap`
Disable snap `$PACKAGE
```sh
snap disable $PACKAGE
```
Enable disabled snap `$PACKAGE`
```sh
snap enable $PACKAGE
```
Display information about `$PACKAGE`
```sh
snap info --verbose $PACKAGE
```
Install snap `$PACKAGE`
```sh
snap install $PACKAGE
```
Display logs of snap `$PACKAGE`
```sh
snap logs $PACKAGE
```
Check for snap updates
```sh
snap refresh
```
Uninstall snap `$PACKAGE`
```sh
snap remove $PACKAGE
```
### `yay`
Display all AUR packages that need to be updated (deprecated)
```sh
yay -Pu
yay --show --upgrades package
```
List all install packages, filtering output to packages that are out-of-date on the local system
```sh
yay -Qu
yay --query --upgrades
```
Install {pkg} from the AUR
```sh
yay -S package
yay --sync package
```
Display information about {package}
```sh
yay -Si package
yay --sync --info package
```
Search for {pkg} in AUR repos
```sh
yay -Ss package
yay --sync --search package
```
Update all packages from AUR and official repos
```sh
yay -Syu
yay --sync --refresh --sysupgrade
```
Remove unwanted dependencies of now-removed installations of AUR repos
```sh
yay -Yc
yay --yay --clean
```
### `yum`
Yellow Dog Updater, Modified package manager (Yellow Dog was a variation of Red Hat for PowerPC architectures), package manager more commonly used today. [[35](sources.md), [37](sources.md)]

Option  | POSIX option            | Effect
:---    | :---                    | :---
`-y`    | `--assumeyes`           | respond to any prompt with "yes" automatically
`-x`    | `--exclude`             | exclude specific packages from updates [[38](sources.md)]

Install {package}
```sh
yum install package
yum groupinstall packagegroup # package group
yum --enablerepo=repo install package # from a specific {repo}
```
Remove {package} 
```sh
yum remove package
yum -y remove package # without confirmation
yum erase package # as well as the cached package
yum groupremove packagegroup
```
Update installed packages
```sh
yum update
yum update package # update a specific {package}
yum upgrade # equivalent to `yum update --obsoletes`
yum groupupdate packagegroup

# Exclude some packages from update
yum update --exclude=kernel
yum update --exclude=httpd,php
```
List all available packages in database
```sh
yum list
yum grouplist
```
List all installed packages
```sh
yum list installed
```
Query repos for information on {package}
```sh
yum info package
```
Find packages
```sh
yum list name # name matching {name} exactly
yum search pattern # search for package name matching {pattern}
```
Find what package {config} belongs to
```sh
yum provides /path/to/config
```
List repositories
```sh
yum repolist
yum repolist all # enabled and disabled repos
```
Interactive shell
```sh
yum shell
```
Clear cache
```sh
yum clean all
```
View command history
```sh
yum history
```