The Display Manager provides the graphical login screen you see when you start your Korora system. It has options for the desktop you will run and allows you to enter your password. Korora uses LightDM as the display manager for Cinnamon, Mate and Xfce.
Korora includes a graphical configuration utility for LightDM. You will find it listed as "LightDM GTK+ Greeter Settings" in System Settings or under Administration depending on the Desktop Environment you are using. It allows the setting of background, theme, user icon. location and a number of other options. It is easy and safe to change the settings in here. None of the settings will break LightDM.

As the display manager is a system function you will need to provide authentication to open the configuration utility. Enter the requested password and the Greeter settings will open. Note any settings that LightDM cannot implement are shown with a asterisk beside them.

The first screen shows the Appearance. The theme, icons, fonts, backgrounds etc are set here. These need to be installed for system wide use.
>Any themes, fonts, backgrounds etc. that have been installed for a specific user only will not work in LightDM. Similarly an image in the user's home directory won't work for the background. To use your own image move it to /usr/share/backgrounds.

The second screen shows the contents of the panel. The items in the panel can be moved, removed or new items added. Clicking on the "+" symbol shows the available panel items. The clock format can be set here too. The clock uses the standard clock formatting options. To review those options type `man strftime` in a terminal. 

The third screen shows the position of the password window. The base position can be set using the graphic at the top of the screen and fine tuned with the settings below. it may take some experimenting to get this position where you prefer it.

The fourth window is for misc. settings and most people will be happy with the defaults.

If you have made changes and want to reset to the previous settings before you save, click on the Reload button in the lower bar. To save your changes click the Save button. Then exit and restart Korora to check your settings.