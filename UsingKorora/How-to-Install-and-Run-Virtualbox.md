## Background
So your computer system is made up of three (main) components:
Physical hardware (computer bits)
Kernel (software which talks to your hardware and makes it work, think drivers)
Software (talks to your kernel to get to your hardware)
Your kernel is what makes your computer work (this is actually what Linux is, a kernel) and it’s actually the most important part of the operating system. When you’re talking about VirtualBox, it needs to create fake hardware on top of your real hardware, so to that, it needs a driver. Drivers sit in the kernel layer.

The Linux kernel has thousands of drivers in it, but it does not have VirtualBox drivers in it (yet). This means you need to compile these and load them into your running kernel of you want to use VirtualBox. Once you do that, your kernel will have the fake hardware that the VirtualBox software needs to run. Drivers which you can load and unload into the kernel are called modules.

The VirtualBox host computer needs these drivers, but the VirtualBox guest also needs some drivers to make full use of the hardware. When you install Linux or Windows as a VirtualBox guest, the hardware is fake, so that OS needs drivers too! Some of those drivers (like audio and network) are already in the Linux kernel, so if your guest is running Linux, you just need drivers for the video, etc.
## Requirements
In order to compile the drivers for VirtualBox (on both host and guest) on Linux you need some development libraries, compiler program (such as GCC), as well as the headers for the running kernel. You need the headers because you need to compile a driver to load into the kernel and it needs to know detailed information about it.

Fortunately, if you’re using Korora, all of the required tools and packages are already installed! :smile: All you need to do is build the drivers.

If you’re running a vanilla instance of Fedora, then you need to install the build tools like so:
`su -c 'dnf install gcc kernel-devel'`
Now you have the build tools required to compile the drivers.

## Automatically building drivers after kernel update
Modules are for a specific kernel and so when you get a kernel update, you need to re-compile the drivers for VirtualBox hosts and guests. Fortunately, there’s a neat little package called DKMS (Dynamic Kernel Module Support Framework) which will do this for you automatically – and of course Korora comes with this pre-installed.

If you’re running Fedora, you can easily install it like so:
`su -c 'dnf install dkms time'`
When you install VirtualBox (see below), it will register the drivers with DKMS and on boot it will re-compile them for you, if it needs to. So, you just need to do it once and forget! Any updates to VirtualBox that are pulled in will also be automatically updated.

## Building drivers on the host
Because Korora has all of the requirements for VirtualBox (including the package repository), all you need to do to get VirtualBox up and running is to install it using the package manager. If you prefer, you can install it manually like so (note the version is currently 4.1):
`sudo yum install VirtualBox-4.3.6`

Again, if you’re using vanilla Fedora, then you need to grab the RPMFusion repository file so that you can install VirtualBox from the Oracle repository (the packaged version from Fedora is usually a few versions behind).
`su -c 'wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo -O /etc/yum.repos.d/virtualbox.repo'`
Now you can install VirtualBox as above.

## Group permissions
Just remember that any user who wants to run and use VirtualBox on the host needs to be in the vboxusers group. You can use the users graphical tool to do this (system-config-users), or add them to the group by running the command (substitute chris with your username):
`sudo gpasswd -a chris vboxusers`
Then just run VirtualBox and away you go!

## Building drivers on the guest
Once you have your host up and your guest operating system installed, the way to install the required drivers is using the built in method. Once you have booted your guest operating system, simply click the Devices menu at the top, and click Install Guest Addons.


This will load a CD in your guest and you can run the autorun.sh script from the disk, which will ask you for the root password and then detect your operating system and compile the drivers for you.


Once again, if your guest is running Korora too, then you already have the required build tools and libraries. If not, you will need to install them first – how this is done depends on your distro (for Fedora, see above).

That’s it! Just reboot your guest and away you go.
