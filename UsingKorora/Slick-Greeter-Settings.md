The Display Manager provides the graphical login screen you see when you start your Korora system. It has options for the desktop you will run and allows you to enter your password. Korora uses LightDM as the display manager for Cinnamon, Mate and Xfce. There are a choice of greeters and you can [select the greeter](https://kororaproject.org/support/documentation/changing-the-lightdm-greeter) to use. This guide covers the Slick Greeter.

Korora includes a graphical configuration utility for LightDM Slick Greeter. You will find it listed as "Login Window" in System Settings or under Administration depending on the Desktop Environment you are using. It allows the setting of background, theme, user icon and a number of other options. It is easy and safe to change the settings in here. None of the settings will break LightDM.

As the display manager is a system function you will need to provide authentication to open the configuration utility. Enter the requested password and the Login Window settings will open. Note any settings that LightDM cannot implement are shown with a asterisk beside them.

![LightDM Slick Settings](https://github.com/kororaproject/kp-documentation/blob/master/img/Slick-Greeter-Settings.png?raw=true)

The first option will create a dotted grid effect over the login screen. The purpose for this is unknown. The next line will show the hostname on the top panel.

There are options for a background logo or a user logo which will appear int helower left corner. 

The theme, icons, backgrounds etc are set next. These need to be installed for system wide use. There is also an option for HiDPI screens.
<div class="callout callout-warning"><p>Any themes, fonts, backgrounds etc. that have been installed for a specific user only will not work in LightDM. Similarly an image in the user's home directory won't work for the background. To use your own image move it to /usr/share/backgrounds.</p></div>

The last option will allow guest logins. It should normally be left off.

If you have amde changes Log Out and back in to check your settings.
