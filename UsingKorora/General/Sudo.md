

**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Sudo](#sudo)
  - [Setting up Sudo](#setting-up-sudo)
  - [Using Sudo](#using-sudo)



# Sudo

Prefacing a command with sudo allows a user to run that command as another user. It is commonly used to run commands, such as dnf, that require administrator permission as a user.

## Setting up Sudo
In Korora Sudo is normally set up during the installation of the system by selecting the Administrator option when creating the user. However it can easily by created after installation. In a terminal run (replacing 'username' with the username of the user).

```
su -c "usermod -g wheel username"
```

You will be asked for the root password.

## Using Sudo

Commands that require authentication can now be run by prefacing them with sudo. When asked for the password enter the user's password. With applications that request authentication it is the user password that is required.

It is still possible to open a root shell by entering `su - ` in a terminal and typing the root password when asked.

For further information see [https://fedoramagazine.org/howto-use-sudo](https://fedoramagazine.org/howto-use-sudo)/.
