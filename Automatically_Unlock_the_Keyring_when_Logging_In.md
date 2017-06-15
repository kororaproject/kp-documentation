LightDM is the default display manager in Korora for Cinnamon, MATE and Xfce. When you start your Korora system it takes you to the LightDM so you can enter your password. However, after logging in you will be asked to enter a password for your Keyring. if you use your user password as the keyring password LightDM can automatically unlock the keyring for you.
>It is always a good idea to backup any important data before modifying system configuration.

### Auto-unlock
It is possible to set LightDM to automatically unlock your keyring when you log in.

Using your preferred text editor open /etc/pam.d/lightdm. You will need root permission to edit this file so use `su -` or prefix the command with `sudo`. Uncomment, by removing the leading `-` from, the following line:
```bash
-auth optional pam_gnome_keyring.so
```