# Installing Korora

Being a Fedora Remix, Korora inherits the [Anaconda](https://fedoraproject.org/wiki/Anaconda) installer for all of our images. Having undergone a massive re-write in 2012 it has seen solid improvements since then. This document walks you through the installation of Korora onto your hard disk. We try to cover common scenarios, including EFI as it is becoming more common these days.

## Before you begin

> It's always a good idea to backup any important data before installing any operating system and Korora is no different.

Korora is able to dualboot Windows, however if you are using Windows 8 or later versions, there are some things you should do before installing Korora.

## Secure boot

Secure boot is _not_ an integral part of EFI, although it should work on Korora you may wish to turn it off. You do this by entering your computer's EFI setup and look for a way to disable it. Unfortunately how you enter the EFI is different with every brand of computer, as is the menu location for disabling Secure Boot.

## Fast shutdown

Windows 8 implements a fast shutdown feature that helps speed up shutdown and startup operations on a single-boot computer. Unfortunately, this feature can cause filesystem corruption if it's used on a multi-boot computer. You can disable the feature under Windows by launching an Administrator Command Prompt and typing:

```
powercfg /h off
```

So let's recap: You've gone to the Korora Download page here:

[https://kororaproject.org/download](https://kororaproject.org/download)

You chose a version of Korora, along with the desktop environment of your choice. Then you've installed the ISO file on a USB stick -- the preferred method of trying out Korora (though you can still burn a DVD and install that way, if need be) -- by using the instructions on the Creating Bootable Media page here:

[https://kororaproject.org/support/documentation/creating-bootable-media](https://kororaproject.org/support/documentation/creating-bootable-media)

Now you're ready to go.

**BUT BEFORE YOU START**, an important note: Installing Korora on your hard drive will delete any currently existing data. **If you wish to keep the data that is currently on the drive before installing Korora, back it up first before performing the Korora installation**.

Let me repeat that: If you have data on the hard drive on which you are about to install Korora, installing Korora will wipe out any data you currently have on that particular drive. So if you want to save some/all of the data on your drive, back it up first.

## INSTALLING KORORA AS A SOLE OS (SINGLE BOOT)

Insert your Live USB drive into your computer and boot (or reboot, if it is already running). Once you are up and running, you will get the desktop screen of your desktop of choice which should automatically have a Korora Welcome window appear in the centre. This window is just a "thank you," along with some buttons which take you to various locations in the Korora infrastructure.

The install program is Anaconda, which is the Fedora Project's installer. Anaconda is a fairly sophisticated installer. It supports installation from local and remote sources such as CDs and DVDs, images stored on a hard drive, NFS, HTTP, and FTP. For more information on Anaconda, visit the Fedora Project's Anaconda page here:

[https://fedoraproject.org/wiki/Anaconda](https://fedoraproject.org/wiki/Anaconda)

So if you click on the icon on the desktop that says "Install to Hard Drive," or click on "Install Korora" from the Korora Welcome window, Anaconda will start. Anaconda will take you through the installation process with the following screens:

### Language

Here you will chose the language with which you will use the new software. Click on Continue in the lower right to go to the next screen, which is

### Installation Summary

Here you will set your Date/Time by the time zone in which you live, set your keyboard preference in Keyboard, set the destination for your installation (your hard drive) in Installation Destination, and set your Network Configuration (note: you need not be connected to install, but it doesn't hurt to be connected during the installation process. The Network Configuration allows you to connect to your network during the install).

Chances are you will get a message under Installation Destination saying "No disks selected" and/or an error message at the bottom in a yellow stripe saying, "Please complete items marked with the icon before continuing to the next step." No need to worry. Go to the item where the icon is and remedy the problem.

For example, if it is under Installation Destination, click on the icon of the hard drive on which you want to install Korora, and then click Done in the upper left. You will get a window telling you how much free space is available/unavailable and and it will bring you to a screen where you can choose the drive on which you wish to install Korora. When you choose your drive, you will get a second window notifying you of your drive's available space, as well as allowing you to choose your partition scheme and a check box to encrypt your data. Using the row of buttons on the bottom, you can also Cancel, Custom Partition and Reclaim Space.

If you are installing on a disk which already has a Linux distro or other operating system on it, you are more than likely going to have to reclaim space using the Reclaim Space feature. Click on the Reclaim Space button in the lower right and this will take you to your current disk mapping. To do a "clean install" of Korora -- wiping the drive and giving Korora a fresh start (and, again, you have backed up the data you want to keep, right?) -- click on the hard disk on the top line and click delete. This will free up the space necessary to install Korora.

Once you do this, you will return to the Installation Summary window and your System field will no longer have the warning icon. If you're ready to install, you can click the Begin Installation button in the lower right corner.

### Configuration

While the software is installing on your hard drive, you can set your Root Password and create your User Account.

Click on the Root Password to create a Root Password for your system. This will be used when updating software and other situations where the root password is required. Once you've completed this step by clicking Done in the upper left, you will be returned to the original screen where you can create a User Account.

To create a User Account, click on the User Account to put in your name, your login and a password for this particular account. Once you have completed this step, click Done in the upper left to return to the original screen for creating Root Password and a User Account.

At this point, the installation should be continuing along, with the progress measured in a bar at the bottom of the page. Once the bar is completely blue, you will get a message saying "Korora is now successfully installed on your system and ready for you to use! When you are ready, reboot your system to start using it!" If you're ready, click on the Done button in the lower right, which will bring you back to your desktop.

From your desktop, you can reboot and start using Korora.

## INSTALLING KORORA AS MULTIPLE BOOT (DUAL BOOT)

There have been reports that scripts such as Easy2boot and Grub4dos conflict with the Grub setup created by Anaconda so their use cannot be recommended.

[To follow]
