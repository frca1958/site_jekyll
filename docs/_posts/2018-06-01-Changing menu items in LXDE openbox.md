---
title: "Create menus in LXDE"
---

## Goal: Create Menus in LXDE

## Refs

- [LXDE](https://wiki.lxde.org/en/Main_Page)
- [Configure openbox](https://www.maketecheasier.com/configure-andcustomize-openbox/)



## Basics

At the bottom of the screen is the panel. LXDE installs the lxpanel.
It can be configured with click-right on the panel.
One of the panel applets is an Application Launch Bar which contains one-click launchers. Click preferences to edit the launchers.
The right-hand side of the preferences window contains the known applications (see further).

An alternative for launching applications is by clicking on the panel lxde startbutton. 
The upper part of the menu agains contains the known applications.

*Note*

LXDE disables the (redundant) lowlevel openbox menu (click-right in the screen). 
It can be enabled in Preferences-> Desktop -> Advanced -> Show Menus and configured with obmenu (```sudo apt install obmenu```).
Check ```man obamenu``` to understand how it works. I do not use it furhter on.

*applications*

Apart from some implicit applications (logout etc), applications are specified using desktop files (extension .desktop).
These desktop files reside system-wide in /usr/share/applications, and user-specified in ~/.local/share/applications.
Usually, an application installs its desktop file as part of the installation. Otherwise, a desktop file needs to be created.
Try ```google <app> openbox .desktop```
The file manager PCManFM (Places->Applications) provides some basic configuration of desktop files (see properties).


### Snaps


Login with the ubuntu-one account if needed (```snap login```). As a result, snap commands can be executed without need of sudo.


**Firefox**
Since I did not install any browser, the default x-www-browser alternative does not exist.
I installed Firefox via snap. To make it known to LXDE, I created the missing alternative file:
```sh
sudo update-alternatives --install /usr/bin/x-www-browser x-www-browser /snap/bin/firefox 10
```
In addition, I had to create an alias for the snap because the snap executor checks arg[0], which is x-www-browser.
```
snap alias firefox x-www-browser
```
There is no need to create a specifi desktop file because x-www-browser is generic.

**Visual Studio IDE**
There is no desktop file. I created one using the icon from te snap installation.
```
[Desktop Entry]
Name=Visual Studio Code
X-GNOME-FullName=Visual Studio Code
Comment=Visual Studio Code
Categories=Development;IDE;
Exec=/snap/bin/vscode
Icon=/snap/vscode/current/usr/share/pixmaps/code.png
Terminal=false
Type=Application
```

