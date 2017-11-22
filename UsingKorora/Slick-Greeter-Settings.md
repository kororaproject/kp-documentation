**Table of Contents**  

- [Appearance](#appearance)
- [Users](#users)
- [Settings](#settings)

The Display Manager provides the graphical login screen you see when you start your Korora system. It has options for the desktop you will run and allows you to enter your password. Korora uses LightDM as the display manager for Cinnamon, Mate and Xfce. There are a choice of greeters and you can [select the greeter](https://kororaproject.org/support/documentation/changing-the-lightdm-greeter) to use. This guide covers the Slick Greeter settings.

Korora includes a graphical configuration utility for LightDM Slick Greeter. You will find it listed as "Login Window" in System Settings or under Administration depending on the Desktop Environment you are using. It provides for the setting of a number of options. It is easy and safe to change the settings in here. None of the settings will break LightDM.

As the display manager is a system function you will need to provide authentication to open the configuration utility. Enter the requested password and the Login Window settings will open. The settings are divided into 3 sections with Tabs to select the three sections at the top of the window. The sections cover appearane settings, options for user access and general settings.

![LightDM Slick Settings1](https://github.com/kororaproject/kp-documentation/blob/master/img/Slick-Greeter-settings1.png?raw=true)

<a name="appearance"></a>
#### Appearance

The first option is the background. You can select to display an image or a plain coloured screen. There is a further option to create a dotted grid effect over the login screen. The purpose for this is unknown

The theme and icons are set next. Then there are options for other pictures. If you have multiple monitors the secondary monitors can display a different image to the main monitor.

You can also display an image or logo in the bottom left hand corner.

<div class="callout callout-warning"><p>Any themes, fonts, backgrounds etc. that have been installed for a specific user only will not work in LightDM. Install any themes and icons for all users.

Similarly an image in the user's home directory won't work for the background. To use your own image move it to /usr/share/backgrounds.</p></div>

<a name="users"></a>
#### Users

![LightDM Slick Settings2](https://github.com/kororaproject/kp-documentation/blob/master/img/Slick-Greeter-settings2.png?raw=true)

These are options that control the user access. Most are self explanatory. The user list can be hidden so only the default (or most recent) user will be displayed. The next option will allow guest logins. It should normally be left off.

The last section allows an automatic login for a particular user. 
<div class="callout callout-warning"><p>Autologin reduces the security of the system as anyone starting the system can access the selected user's data without knowledge of the password. It should not be enabled without consideration of the security implications.</p></div>

<a name="settings"></a>
#### Settings

![LightDM Slick Settings3](https://github.com/kororaproject/kp-documentation/blob/master/img/Slick-Greeter-settings3.png?raw=true)

The final section is for general settings. It includes a section on the additional information that will be displayed on the LightDM screen.

The first option will activate the numlock on keyboard with separate numeric keypads.

The next option is for HiDPI screens. If you have a HiDPI monitor that isn't properly recognised you may need to explicitly set it here however most users will be happy with the default Auto setting.

The next section covers the items that appear in LightDM's top panel. Most people will be happy with the defaults but feel free to experiment. E.g. if you are on a desktop you may wish to turn the Battery power indicator off. 

Some settings are marked to indicate a reboot is required for your changes to be activated but for any other changes Log Out and back in to check your settings.
