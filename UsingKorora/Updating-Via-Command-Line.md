## Updating via command line

Korora has a command line which is extremely powerful and flexible. Learning how to use it is something that all good Linux users should be able to do without being scared. Here's how to update your system using the command line.

While you can use a GUI to update your system, many users prefer the command line because it's more lightweight and easier to see what's going on and can easily be scheduled.

The primary package management tool is _dnf_ which can not only install and remove packages but update your entire system.

Open up a terminal and become root.

```
sudo -i
```

If you want to, you can clean local metadata and force an update from the remote servers, but this isn't necessary as the --refresh option does much the same.

```
dnf clean all
```

Update all packages.

```
dnf --refresh upgrade
```

> If you need to restart the update, e.g. when a package fails to download, remove the --refresh option from the command

<br />

>If the update included a new kernel or other major system package you should reboot the system. If a new version of your desktop environment has been provided you should log out and back in.
