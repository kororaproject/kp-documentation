LightDM is the default Display manager in Korora for Cinnamon, Mate and Xfce. When you start your Korora system it takes you to the LightDM so you can enter your password. However if you are the only user of the system you may prefer to bypass this screen and have Korora go straight to the desktop.
>It is always a good idea to backup any important data before modifying system configuration.

### Autologin
It is possible to set Lightdm to log in to the default user without asking for a password.
>Autologin reduces the security of the system as anyone starting the system can access the default user's data without knowledge of the password. It should not be enabled without consideration of the security implications.

Using your prefered text editor open /etc/lightdm/lightdm.conf. You will need root permission to edit this file so use `su -` or prefix the command with sudo. Locate the section headed `[SeatDefaults]`. Scroll down to the line starting with `#autologin-user=` and remove the `#` to uncomment the line. Add the name of the user to be logged in. The following line, `#autologin-user-timeout=0`can be edited to give access to the login screen and a delay before the system logs in. Uncomment the line and increase the setting to equal the number of seconds required. (There are some reports of Autologin not working with a timeout value greater than 0, please test with 0 before reporting a problem).

### Additional Steps for Mate
For Mate you also need to scroll down to the line starting with `#user-session=` and remove the `#` to uncomment the line and edit it to show `user-session=mate`.

An alternative method is to use sed - 

`sudo sed -i 's/^#autologin-user=.*/autologin-user=liveuser/' /etc/lightdm/lightdm.conf`

`sudo sed -i 's/^#autologin-user-timeout=.*/autologin-user-timeout=0/' /etc/lightdm/lightdm.conf`

You also need to set MATE as default session, otherwise login will fail `sudo sed -i 's/^#user-session=.*/user-session=mate/' /etc/lightdm/lightdm.conf`