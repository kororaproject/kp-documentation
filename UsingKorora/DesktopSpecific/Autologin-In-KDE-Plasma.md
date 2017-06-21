

**Table of Contents**  

- [Autologin in KDE Plasma](#autologin-in-kde-plasma)
  - [Autologin](#autologin)



# Autologin in KDE Plasma

When you start your Korora system it takes you to the SDDM so you can enter your password and start Plasma. However if you are the only user of the system you may prefer to bypass this screen and have Korora go straight to the desktop.

>It is always a good idea to backup any important data before modifying system configuration.

## Autologin

It is possible to set SDDM to log in to the default user without asking for a password.

>Autologin reduces the security of the system as anyone starting the system can access the default user's data without knowledge of the password. It should not be enabled without consideration of the security implications.

KDE provides a graphical setting screen for SDDM. Start "System Settings" and select "Startup and Shutdown". The first option is for SDDM. Select the Advanced tab. Check the Autologin box and confirm the correct user and session are shown. Click on Apply. KDE will now automatically start Plasma and log in the selected user.
