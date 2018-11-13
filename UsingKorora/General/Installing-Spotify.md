**Table of Contents**  

- [Installing Spotify](#installing-spotify)
- [Updating Spotify](#updating-spotify)


<a name="installing-spotify"></a>
# Installing Spotify

Spotify is a popular streaming service and provides a client to access the service. It isn't open source and the license prohibits redistribution however it is possible to install it using Korora's package manager or from the command line using dnf. You will need to create a Spotify account to use this application.

The RPMFusion repository provides a Local Package Factory package that downloads and installs Spotify and its required dependencies.

To install type 
```
sudo dnf install lpf-spotify-client
```
When it is installed run lpf-spotify-client from the menu. Depending on the desktop environment you use it will appear in the System or similar area. It will handle the download and installation of Spotify. Just follow the instructions on the screen. You will be asked for your password to authorise installation and also need to click OK in a confirmation screen to accept licence terms. 

When it is complete Spotify Client will appear on the Multimedia section of your menu. You can create a new Spotify account or sign in with an existing account.

<a name="updating-spotify"></a>
# Updating Spotify

When a new version of Spotify client is released you can update by running lpf-spotify-client from the menu again. It will recognise that a new version is available and repeat the download, build and install process for you.
