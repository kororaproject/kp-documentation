**Table of Contents**  

- [Installation](#installation)
- [Configuration](#config)
- [Settings](#settings)

LightDM is a display manager which handle the initialisation and login to several Korora desktop environments. While LightDM processes the login it doesn't include the graphical login screen which is known as the greeter. There is a choice of greeter screens in the repos and there may be others available elsewhere.

Mate and Xfce use the GTK+ greeter as did Cinnamon until version 26. Cinnamon now uses the Slick greeter. However they are interchangeable and you can replace the included one with an alternative.

The GTK+ Greeter as used in Mate and Xfce

![LightDM_Greeter_GTK](https://github.com/kororaproject/kp-documentation/blob/master/img/Lightdm-Greeter-GTK.png?raw=true)

The Slick greeter as used in Cinnamon.

![LightDM_Greeter_Slick](https://github.com/kororaproject/kp-documentation/blob/master/img/Lightdm-Greeter-Slick.png?raw=true)

<a name="installation"></a>
### Installation
To see the available greeters type `dnf list *greet*` and you will see something like
```
Installed Packages
lightdm-gtk-greeter-settings.noarch
slick-greeter.x86_64 

Available Packages
kgreeter-plugins.x86_64 
lightdm-autologin-greeter.noarch
pantheon-greeter.x86_64 
```
The actual packages shown may differ on other versions. Ignore the Kgreeter, it isn't part of LightDM. The autologin greeter is a special greeter for kiosk setups and not for general use. 

To install another greeter, e.g. the Slick Greeter,  type `dnf install slick-greeter`. This command needs to be run as root using `su -` or prefixed with sudo.

<a name="config"></a>
### Configuration
To see the available greeters in your system, type `ls -l /usr/share/xgreeters`, it will show something like
```
-rw-r--r--. 1 root root 187 Aug 22 17:13 lightdm-gtk-greeter.desktop
-rw-r--r--. 1 root root 131 Jul  7 09:48 slick-greeter.desktop
```
The important information is the name of the .desktop files. So the GTK+ greeter is called 'lightdm-gtk-greeter' and the Slick greeter is 'slick-greeter'.

To activate the desired greeter edit /etc/lightdm/lightdm.conf. To do this, we need to edit the file as root (substitute _nano -w_ for your favourite editor, such as  _kwrite_ for KDE).

```bash
sudo nano -w /etc/lightdm/lightdm.conf
```
Change the greeter-session line in 'seat', replacing the name there with the name of the desired greeter and uncommenting the line. E.g. when set up for the Slick greeter, the first few lines of the Seat section will look like 
```
[Seat:*]
#type=xlocal
#pam-service=lightdm
#pam-autologin-service=lightdm-autologin
#pam-greeter-service=lightdm-greeter
#xserver-command=X
#xmir-command=Xmir
#xserver-config=
#xserver-layout=
#xserver-allow-tcp=false
#xserver-share=true
#xserver-hostname=
#xserver-display-number=
#xdmcp-manager=
#xdmcp-port=177
#xdmcp-key=
#unity-compositor-command=unity-system-compositor
#unity-compositor-timeout=60
greeter-session=slick-greeter
```

<a name="settings"></a>
### Settings
Both the Slick Greeter and the GTK+ Greeter provide a Settings options application. The Slick Greeter app is called "Login Window" while the GTK+ Greeter is called "[LightDM GTK+ Greeter Settings](https://kororaproject.org/support/documentation/lightdm-greeter-settings)". They will be found in the Adminstration settings section of the menu or Settings Manager.
