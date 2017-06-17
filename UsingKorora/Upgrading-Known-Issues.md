# Upgrading - Known issues

Using the upgrade facility is a simple way to move to Korora 24 without the need of a full installation. Your data, settings and installed applications are still there and you can keep working on your system for much of the process. There are a few known issues that may appear during the process, although they are all easily handled and the upgrade process should then proceed as expected.

## Package Errors

The most common issues are two packages that give an error that states "none of the providers can be installed." These packages are lirc-core and sigrok-firmware-free. It is safe to remove these packages. You can run the following command to remove them:

```
sudo dnf remove lirc-core sigrok-firmware-free
```

As these are drivers and firmware for rare hardware (infra-red and electronic test equipment) you probably won't need them. However if you do, it is safe to re-install them again after you have upgraded to 24.

There is another package conflict that affect KDE upgrades. There will be a message that includes `kdm-settings-1:4.11.22-16.fc24.noarch conflicts with file from package kde-settings-kdm-1:23-7.fc23.2.noarch`. As kde-settings-kdm is an integral part of KDE it must be handled carefully. It should be removed but without removing any dependencies. It can be removed with` rpm -e --nodeps kde-settings-kdm`.

As Pharlap is no longer supported it should be removed too

```
sudo dnf remove pharlap*
```

## Sudo

A less common issue reported by some users is that sudo doesn't work but logging into a terminal as root, i.e. using **su -**, does. This has not yet been confirmed.

## User Installed Applications

Another issue that has affected a small number of people is the existence of applications installed outside of the package manager. These are usually built from source after installing the required dependencies. As those dependencies may have been updated these applications may not run or may give errors. It is advisable to re-build and or re-install these applications using the same process that was done originally. This is a good opportunity to check if they have been updated and to install the latest version.

## Third party Repos

Similarly any non-standard or third party repos that have been added to the system may need to be disabled. If you see any errors connected with packages installed from those repos remove the packages and disable the repos. After the upgrade is complete the repos can be re-enabled if they have support for 24 and the packages can be installed.

## LightDM

All desktop apart from Gnome and KDE use LightDM. It controls the Log In screen.

Although it will not cause any operational issues some of the LightDM settings need updating. the LightDM Greeter Settings will be on the Administration part of your menu. When run it will show a coloured exclamation mark on any setting that needs attention. Common ones are the theme and Icon them settings. These need to be set to Arc and Numix-Circle respectively.

## Xfce Settings

Due to the way Xfce settings need to be stored there are an adjustment that needs to be made after the upgrade is complete. The default icon set has changed from Korora to Numix Circle. The Korora icons were an extended version of the Numix Circle theme and the additions we made have been added to the upstream theme. Go to Settings - Appearance - Icons and select Numix-Circle. You may need to update the Appearance theme to one which is GTK3.20 compatible too. Korora 24 & 25 use Arc. The Arc theme can be added with

```
sudo dnf install arc-theme
```

If you experience any issues not listed here please let us know on irc or on Engage.
