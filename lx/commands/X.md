### `X`
Start the graphical interface from a command line\
Test X11 with the config file automatically generated after `Xorg -configure`
```sh
X -config $HOME/xorg.conf.new
```
### `xdpyinfo`
Show detailed information about display
### `xhost`
Enable access control to X server
```sh
xhost -
```
Remove {host} from list of authorized clients for X server
```sh
xhost -host
```
Disable access control to X server
```sh
xhost +
```
Add {host} to list of authorized clients for X server
```sh
xhost +host
```
Add user `dpezet` to ACL
```sh
xhost si:localuser:dpezet
```
Allow clients from any host to connect (not unsafe if you use a firewall that allows only SSH)
```sh
xhost +
```
### `xlsclients`
Determine what applications are running on the legacy X11 server provided with Wayland.
### `xmodmap`
Replacing Caps Lock with Escape
```
! Swap caps lock and escape
remove Lock = Caps_Lock
keysym Escape = Caps_Lock
keysym Caps_Lock = Escape
add Lock = Caps_Lock
```
### `Xorg`
Enable automatic configuration of X11 server
```sh
Xorg -configure
```
### `xrandr`
Set size, orientation, and reflection of video output\
Change resolution of DisplayPort1 to 1920x1080
```sh
xrandr --output DP1 --mode 1920x1080
```
Disable VGA1 output
```sh
xrandr --output VGA1 --off
```
Display current state of the system
```sh
xrandr -q  --query
```
### `xwininfo`
Utility that provides information about a clicked window, including dimensions, position, etc