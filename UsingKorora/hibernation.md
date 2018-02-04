Hibernation is the ability to pause your Korora system and resume exactly where you were at a later time. Unlike Suspend which needs power Hibernation requires no power and so can be resumed at any future tme. 

Suspend will use the computer's memory to retain the session information. This has the advantage of being much faster, almost intantanneous. However is power is lost the session is lost too. Hibernation uses the swap partition to save the session information and so will retain that information indefinitely.

By default hibernation is not set to be operational on Korora systems. It needs to be configured in the boot options by defing a resume device. This is your swap partition.

To set a resume device you need to add `resume=/dev/sdxn` to /etc/default/grub (changing the x and n to the correct device for the swap partition). Then run `grub2-mkconfig -o /boot/grub2/grub.cfg` (or if on an efi system /boot/efi/EFI/fedora/grub.cfg, if not sure use command completion to show the correct path). Use sudo or run this command as root.
