# bc-development-machine
Description of my setup for the Blockchain hackathon

# Ubuntu setup
Start with Ubuntu 16.10 server from Azure

```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install ubuntu-gnome-desktop -y
sudo apt-get install gnome-panel metacity -y
sudo apt-get install tightvncserver -y
tightvncserver
```
Then enter the vnc password and kill the server with:
```
tightvncserver -kill :1
```

Fix some config:
```
nano .vnc/xstartup
```

Change the content to:
```
#!/bin/sh

export XKL_XMODMAP_DISABLE=1
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS

[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &

gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
gnome-terminal &
```


# SSH setup
Tunnel from 5901 (standard tightvncserver port) to localhost:5901

# Install TightVNC
From tightvnc.com [http://www.tightvnc.com/]

Connect to ```localhost:5901```

# Make everything look better
Gnome shell [https://www.maketecheasier.com/8-gnome-shell-themes/]
Terminal [https://github.com/denysdovhan/one-gnome-terminal]
