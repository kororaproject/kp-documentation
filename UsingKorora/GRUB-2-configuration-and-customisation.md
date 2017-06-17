GRUB 2 has been the default bootloader for Fedora and Korora for a number of releases. This is a short guide on tweaking the common settings, such as themes.
![img/GRUB_2_configuration_and_customisation.png](https://github.com/kororaproject/kp-documentation/blob/master/img/GRUB_2_configuration_and_customisation.png)

>It is always a good idea to backup any important data before modifying system configuration.
## Files
Unlike legacy GRUB where there was a single running configuration file, with GRUB 2 there is a default configuration file and a command line tool that generates the running config.

There are a couple of important files.

**/boot/grub2/grub.cfg** or on EFI systems **/boot/efi/EFI/fedora/grub.cfg** – this is the file that GRUB 2 uses to boot the system. It contains all the configuration options but should not be edited. View this file to see the current running configuration and what options there are. If you do edit this file, the changes will be lost once you run the GRUB tool, _grub2-mkconfig_.

**/etc/default/grub** – this file contains the options used to create the running _grub.cfg_ config and is expected to be edited (as root).

## Rebuilding running configuration
As we mention above, you do not edit the running GRUB 2 configuration file in GRUB 2 but rather run a tool after you have made changes to the default config file, */etc/default/grub*.

This is how you rebuild the config.

```bash
sudo grub2-mkconfig -o /boot/grub2/grub.cfg

or for EFI system sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg
```

Unlike legacy GRUB, this step needs to be repeated every time you change the default GRUB 2 configuration.

## Making changes
As with previous versions you can call up the running GRUB menu when you turn on your computer by pressing any key before the kernel loads and use the edit options there for one time changes. This is a good way to test a change before you add it permanently to the config file. Simply follow the on-screen instructions to do this.

When you have the correct combination of changes, you can make them permanent by changing the default boot options. To do this, we need to edit the file as root (substitute _nano -w_ for your favourite editor, such as _gedit_ for GNOME or _kwrite_ for KDE).

```bash
sudo nano -w /etc/default/grub
```

If you need to add or modify boot options to the kernel line you will need to edit the *GRUB_CMDLINE_LINUX* entry. Remove or add what you need, ensuring that you don't remove the closing (“) mark.

If you don’t have a dual boot system you could change the line *GRUB_TIMEOUT=5* and replace the 5 with 0. This is the number of seconds that the GRUB menu will appear, just as in legacy GRUB. It is a good idea to change this last, once you have every thing else working as it makes it simpler if you need to change the boot command while experimenting.

Now rebuild your running configuration using the _Rebuilding Running Configuration_ instructions above, you can reboot and test your changes!

## Adding a background
Korora has a basic white on black screen which is functional but doesn't look too good. If you prefer a background, as in previous versions, there are a few steps involved.

First, create a GRUB compatible font file from an existing system font file (we chose _DejaVu Sans Mono_ but you can use any you like).

```bash
sudo grub2-mkfont --output=/boot/grub2/unicode.pf2 /usr/share/fonts/dejavu/DejaVuSansMono.ttf
```

Then enable graphics mode in the GRUB 2 default config file, */etc/default/grub*.

```bash
GRUB_GFXMODE=auto
GRUB_GFXPAYLOAD_LINUX=keep
GRUB_TERMINAL=gfxterm
GRUB_BACKGROUND=/usr/share/backgrounds/korora/default/normalish/korora.png
```

If the "auto" setting in the *GRUB_GFXMODE* does not detect the screen size correctly you may specify a size as *widthxheight* e.g 1024x768 or *widthxheightxdepth* e.g. 1280X1024x16.  
You can substitute any similarly sized *.png* or *.jpg* file for the background, just specify the path at the *GRUB_BACKGROUND* variable.

Now rebuild your running configuration using the _Rebuilding Running Configuration_ instructions above, you can reboot and test your changes!

## Changing the colours related to the fonts

#### 1 – First of all, open the 41_custom file with your favourite editor.

```bash
sudo nano -w /etc/grub.d/41_custom
```

#### 2 – In that file between the lines _fi_ and _EOF_ add these two lines.

```bash
set color_normal=white/black
set color_highlight=yellow/cyan
```

Please be careful as it may corrupt this file and give you errors when updating your running config file if not done correctly.

Here is an example *41_custom* file.

```bash
cat <<EOF
if [ -f  $prefix/custom.cfg ]; then
source $prefix/custom.cfg;
fi
set color_normal=white/black
set color_highlight=yellow/cyan
EOF
```

<a href="http://members.iinet.net/~herman546/p20/GRUB2%20Splashimages.html#Splashimage_Font_Colors" title="Here">Here</a> is a nice explanation and the list of the colours supported by GRUB 2 (please ignore the 05_debian_theme as it's not related to Fedora/Korora).

#### 3 – Generate your new grub.cfg file.

Now rebuild your running configuration using the _Rebuilding Running Configuration_ instructions above, you can reboot and test your changes!

## Seeing startup details
Some of us prefer to see what is happening when the system boots rather than the pretty animations that Plymouth provides. There are two ways to achieve this, edit the GRUB config or change the Plymouth theme.

#### 1 – Editing GRUB configuration

Edit the default GRUB 2 config file as root (substitute _nano -w_ for your favourite editor, such as _gedit_ for GNOME or _kwrite_ for KDE).

```bash
sudo nano -w /etc/default/grub
```

Find the *GRUB_CMDLINE_LINUX* entry and remove *rhgb* from the line and saving the file.

Now rebuild your running configuration using the _Rebuilding Running Configuration_ instructions above, you can reboot and test your changes!

#### 2 – Change Plymouth theme

List the available Plymouth themes.

```bash
plymouth-set-default-theme --list
```

Here's an example of what you might see.

```bash
change 
details
korora
text
```

The Plymouth theme that provides all the details of the boot is called *details* and so we simply tell Plymouth to use that theme.

```bash
sudo plymouth-set-default-theme details --rebuild-initrd
```

That command will take a short time to finish, simple reboot when it does to see the results!

## More information
A Korora user provided a Korora Grub2 theme, see <https://kororaproject.org/support/engage/thank/korora-grub-theme-1>

There is a page on the Fedora Wiki covering some additional options – <https://fedoraproject.org/wiki/Grub2>, also see <http://forums.fedoraforum.org/showthread.php?t=275112>.

Information on GRUB themes here – <https://github.com/Generator/Grub2-themes#faq> and <http://forums.fedoraforum.org/showthread.php?t=278536>.