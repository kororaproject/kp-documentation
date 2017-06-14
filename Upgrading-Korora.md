# Upgrading Korora

Korora uses Fedora's tools, so upgrading is easy! Here we'll will show you how to upgrade from one release to a new one.

> This should work reliably, however you still do so at your own risk (like any upgrade). If this fails, then you will need to perform a re-install so please make sure you've backed up important data.

<br />

> Contact us on [Engage](https://kororaproject.org/support/engage) if you have any problems!

<br />

> There are a few [known issues](/Upgrading-Known-Issues.md) that should be reviewed before proceeding.

## Upgrading to the latest release

The upgrade is performed with the help of a plugin to the system's package manager, dnf (previously there was a dedicated tool called FedUp).

When run, dnf will:

- Update your version 24 repositories to point to the 25 release
- Download all the rpms required to upgrade your packages
- Reboot your machine and install them
- Boot into your upgraded system

First, make sure you are running the latest packages for your current version.

```
sudo dnf --refresh upgrade
```

Install the dnf system upgrade plugin, in case it's missing (it might already be installed).

```
sudo dnf install dnf-plugin-system-upgrade
```

Run the dnf system upgrade command (this will take a while to download all the updates, but you can continue using your machine in the meantime).

```
sudo dnf --refresh system-upgrade download --releasever=25
```

> If you have an issue and need to restart the system-upgrade remove the '--refresh' option from the command to use packages already downloaded.

You'll be asked to accept and verify the signing keys. Enter `Y` for each key.

Next, tell your system to reboot and perform the upgrade.

```
sudo dnf system-upgrade reboot
```

> There may be no display during this part of the process, however the system will install the upgrades and then reboot.

Finally, your system should reboot into the freshly upgraded system.

You're now ready to enjoy your upgraded system.

## Optional: Upgrade the Rescue Kernel

> This should be left until the upgraded system is tested and works reliably.

The rescue kernel option on the Grub boot menu isn't updated during the upgrade process. To force it to be upgraded to the new version it is necessary to rebuild the Grub configuration. To do this run

```
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```

or for EFI systems

 ```
sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```
