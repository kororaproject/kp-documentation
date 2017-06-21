

**Table of Contents**  

- [QT Theming on GTK Desktops](#qt-theming-on-gtk-desktops)
  - [qt5ct](#qt5ct)
  - [Qt-config](#qt-config)



# QT Theming on GTK Desktops

There are 2 common toolkits used to create applications and desktops in Linux systems. These are GTK and Qt. All desktops in Korora apart from KDE Plasma are built on GTK, Plasma is built on Qt. However most applications are built on one or the other. There are a few applications such as Dnfdragora which come with GUI interfaces for both toolkits but most only use one. It is fine to use QT applications on GTK desktops however they may not honour the look and feel of GTK themes.

The toolkit used will affect how an application looks on your desktop. Few desktop themes support both GTK and Qt. If you are running an application built on Qt on a GTK desktop there are a couple of configuration options that will help make them look at home among your GTK applications. Which one you use will depend on the version of Qt used to build the application. You may be able to work which your application uses by checking the dependencies installed with it or by checking the About information in its help section.

The latest version is 5 and qt5ct is used to configure Qt5 applications. Those built for the older Qt4 need qt-config. Fortunately both are in the repos.

>Some QT applications include appearance settings in their Preferences. These may be used as well to mimic the appearance of your GTK theme. Try setting the general configuration with the Qt config utilities and then fine tune within the application.

## qt5ct

qt5ct can be installed with `sudo dnf install qt5ct`. Once installed qt5ct will appear in your menu as "Qt5 Settings". The actual location will depend on your desktop but check under Settings or similar.

When launched there are several tabs but the main tab is the first one, "Appearance". The style option shows a number of choices. Try the gtk option first. It will attempt to copy the GTK style theming and make the appearance of the Qt application resemble your selected GTK theme.

If that isn't what you want try the others. If none are suitable you can create a colour palette so it at least matches the GTK colours. For most people this can be left as default as the colours will be set along with the theme The lower half of the screen shows how the application will look.

The other tabs are less important but you may choose to set the font. The icon theme should be set the same as in GTK. (The default icon theme for Korora in Numix Circle).

Under Interface there are several options. You can even select to have some visual effects. The other options are personal preference and many people will be happy with the defaults.

The final tab is for a custom style sheet. Usually this will be left blank.

## Qt-config

qt-config can be installed with `sudo dnf install qt-config`. Once installed it will appear in the menu as "Qt4 Config". The actual location will depend on your desktop but check under Settings or similar.

Qt-config has one advantage over qt5ct. It includes some helpful information in the left hand pane.

Operation is similar to qt5ct but the screens are a little different. Again under "Appearance" select the gui style as GTK. It will try to copy the GTK style theming and make the appearance of the Qt application resemble your selected GTK theme. The lower half of the screen shows how the application will look.

The other tabs cover fonts and the interface which has settings for effects and feel. In all the tabs read through the useful information in the side panel before changing any settings.
