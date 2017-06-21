

**Table of Contents**  

- [Installing Other Desktops](#installing-other-desktops)
  - [Why would you install other DEs?](#why-would-you-install-other-des)
  - [Installation](#installation)
  - [Method 1.](#method-1)
  - [Method 2.](#method-2)
  - [Removing the New Desktop](#removing-the-new-desktop)



# Installing Other Desktops

Korora comes with a choice of a number of desktop environments (DEs) however as Korora is based on Fedora there is a large range of alternate environments and window managers you can add to Korora. These include Openbox, LXDE, Sugar and E17 from the Fedora repos and E18 Enlightenment and LXQT are available from external repos. You can also add another of desktops Korora offers.

## Why would you install other DEs?

Each has its own features and advantages e.g. Enlightenment and the various *Box variants are known to be very light and so work well on older, slower hardware (or blazingly fast on new hardware :) ) or you may want to try the latest DE like LXQT. Sugar is designed as a learning environment for children. You can have as many DE’s as you want or have disk space for.

## Installation

Before following either of these methods it is best to do a full update sudo dnf --refresh upgrade. If you get any major updates including a new kernel, reboot.

> It is always a good idea to backup any important data before modifying system configuration.

## Method 1.

You can install any DE with the command `sudo dnf install @de-desktop` where de is the desktop name, e.g. `sudo dnf install @lxde-desktop` will install Lxde. However this will bring in the entire desktop including many applications which will duplicate applications you already have installed e.g. each desktop environment has its own file manager. A better way is to use Yumex as in the second method.

When it completes log out or reboot. At the login screen you will have the option to select the new environment. The environment you last logged into will be the default for future logins until you manually select a different one.

## Method 2.

Yumex is the graphical front end for the command line yum command. It is included with Korora and in the menu. Yumex lets you easily select and unselect packages, showing you basic information on each package to help you choose and it will then install the selected packages.

> Yumex is no longer under development. See this news item for more information.

As an example we will install Xfce in Korora.

Start Yumex. It will check for updates but shouldn’t find any if you just did an update. Select the Check box for Groups, on the left panel click the arrow for Xfce.

This reveals a number of groups for the Xfce desktop, select the Xfce group. Looking at the right panel it shows as checked the packages that will be installed. Any already installed are shown in green. Optional packages are listed but not checked and in black. Look through the list and uncheck any package you don’t want. You will probably want everything in the base Xfce group. Repeat for the other groups such as applications, multimedia. You may not want to install everything from these groups, e.g. as Korora comes with the most popular multimedia applications you probably won't select anything in the Multimedia group. Clicking on the package will show basic information about it below. Repeat for the other Xfce groups.

Click apply and Yumex will process the dependencies and show what it is going to do. Click OK when you are ready and the packages will be installed.

If you install a desktop such as Xfce that is available in Korora you should install the Korora settings for that desktop too. There may be other Korora additions for a desktop too. To install the Korora packages type sudo `dnf install korora*desktopname` replace desktopname with the desktop you are installing, e.g. the command for Xfce is `sudo dnf install korora*xfce.
`
When it completes log out or reboot. At the login screen you will have the option to select the new environment. The environment you last logged into will be the default for future logins until you manually select a different one.

Explore and try something new.

## Removing the New Desktop

The new desktop can be left in the system even if you don't use it. Using the reverse commands to those above, i.e. replacing the install with remove, will remove packages needed by your system and so should never be done.

If you wish to remove the new desktop and you haven't made any other changes to the packages on your system you can use the `dnf history undo` option to remove the newly installed packages. If you have made changes the undo option may still work but the more changes that have been made will reduce the chances of success. If dnf can not undo the procedure it will refuse to do so to protect your system.
