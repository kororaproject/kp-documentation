# Xfce Terminal Dropdown Option

Many people prefer a dropdown terminal in place of the traditional separate application. Dropdown, sometimes called quake style, terminals allow you to have a terminal open with quick access using a hotkey and without using screen space. The current Xfce terminal has a drop down option. However it is not obvious to most people.

![](https://github.com/kororaproject/kp-documentation/wiki/img/Xfce4-Terminal.png)

It is a hidden option for the standard xfce4-terminal. To access it you need to start the terminal with the command

```
xfce4-terminal --drop-down
```

The man page gives more details and suggests you bind that command to a keyboard shortcut. That way you can press the key to open the terminal and pressing it again will hide but not close the terminal. This means there is no need to add it to your sessions or Autostart. The first time the key is pressed will launch and open it. Further presses will reveal or hide it.

I would suggest binding it to F12. To do this right click on the desktop, select Applications – Settings – Keyboard. Select the Application Shortcuts tab, click on the Add button, type in the command as above. Click OK and it will open another window asking for the key, press your chosen key(s) and the window will close. Test the shortcut, the terminal should open as a drop down.

In Edit there is a preferences option with a new DropDown tab. Make your choices here for size, location etc. If you turn off the menu bar you can access the preferences and new tab etc. options with a right click. The Dropdown preference screen also has an option for Opacity this applies to the whole terminal including the text. The Opacity option on the Appearance tab only affects the background.

There is an option for a panel indicator too, it will appear in the notification area. Clicking on the panel icon will open the terminal. Right clicking gives access to the Preferences and an option to close the terminal.

This is a great option for Xfce users wanting the convenience of a drop down terminal.
