

**Table of Contents**  

- [Cinnamon Shortcuts](#cinnamon-shortcuts)
    - [Changing the Default Shortcut Keybindings](#changing-the-default-shortcut-keybindings)
    - [Emergency Shortcuts](#emergency-shortcuts)
        - [Launch a Console Terminal](#launch-a-console-terminal)
        - [Restart Cinnamon](#restart-cinnamon)
        - [Shut Down](#shut-down)
    - [Session Shortcuts](#session-shortcuts)
        - [Lock Screen](#lock-screen)
        - [Log Out of Current Session](#log-out-of-current-session)
    - [Workspace Shortcuts](#workspace-shortcuts)
        - [Switch to left workspace](#switch-to-left-workspace)
        - [Switch to right workspace](#switch-to-right-workspace)
        - [Send current window to left workspace](#send-current-window-to-left-workspace)
        - [Send current window to right workspace](#send-current-window-to-right-workspace)
    - [Launchers](#launchers)
        - [Launch the GNOME Terminal](#launch-the-gnome-terminal)
        - [Launch Nemo File Manager](#launch-nemo-file-manager)
        - [Launch the Menu Application and Search Bar](#launch-the-menu-application-and-search-bar)
    - [Window Management](#window-management)
        - [Cycle between open windows / applications](#cycle-between-open-windows--applications)
        - [Cycle between open instances of the same application](#cycle-between-open-instances-of-the-same-application)
        - [Show Desktop](#show-desktop)
        - [Snap current window to left side of screen](#snap-current-window-to-left-side-of-screen)
        - [Snap current window to right side of screen](#snap-current-window-to-right-side-of-screen)
        - [Snap current window to top of screen](#snap-current-window-to-top-of-screen)
        - [Snap current window to bottom of screen](#snap-current-window-to-bottom-of-screen)
    - [Screenshots](#screenshots)
        - [Take a Screenshot](#take-a-screenshot)
        - [Take Screenshot of the Current Window](#take-screenshot-of-the-current-window)
        - [Take Screenshot of Selected Area](#take-screenshot-of-selected-area)
        - [Record the Desktop](#record-the-desktop)



<a name="cinnamon-shortcuts"></a>
# Cinnamon Shortcuts

The Cinnamon desktop environment has a number of built-in shortcuts for manipulating the system's resolution, switching workspaces, and launching applications. Mastery of these shortcuts will greatly reduce the amount of time spent clicking around menus and potentially boost your productivity.

**NOTE**: We will not cover all of the available shortcuts. You can look at the Keyboard menu discussed below in order to see them all. This article will cover some of the ones you are most likely to use.

**NOTE on Key Terminology**:

 * If your keyboard came from a Mac, the `Alt` key might be labeled `Option` instead.
 * If your keyboard came from a Mac, you likely have a `Command` key. If you have a Windows-based keyboard, you likely have a Windows key. These keys are referred to in the Linux world as the `Super` key (or `Meta` key in emacs and a few other contexts)
 * The \` key is sometimes called the `grave` or `backtick`. It is usually found above the Tab key, and shares its key with the tilde (~).

<a name="changing-the-default-shortcut-keybindings"></a>
## Changing the Default Shortcut Keybindings

We will be discussing the shortcuts as they exist on a freshly-installed instance of Korora Cinnamon. However, if you would like to change the default shortcuts to better suit your keyboard or workflow, you are free to do by opening the Keyboard settings application, which can be reached by navigating through the following menu path:
**Menu -> Preferences -> Keyboard -> Shortcuts**
or
**Menu -> Preferences -> System Settings -> Hardware -> Keyboard -> Shortcuts**

![keyboard-shortcuts](https://github.com/kororaproject/kp-documentation/wiki/img/cinnamon-keyboard_shortcuts_window.png "Keyboard Shortcuts window") 

<a name="emergency-shortcuts"></a>
## Emergency Shortcuts

<a name="launch-a-console-terminal"></a>
### Launch a Console Terminal

If Cinnamon becomes unresponsive or you need to otherwise access a text-only console terminal outside of the window manager, enter the following command:

    Ctrl + Alt + F2

You can switch back to the GUI by hitting:

    Ctrl + Alt + F1

<a name="restart-cinnamon"></a>
### Restart Cinnamon

If Cinnamon has become buggy or unusable, you can try restarting it via the following:

    Ctrl + Alt + Escape

<a name="shut-down"></a>
### Shut Down

    Ctrl + Alt + End

<a name="session-shortcuts"></a>
## Session Shortcuts

<a name="lock-screen"></a>
### Lock Screen

    Ctrl + Alt + L

**NOTE**: On GNOME and some other desktop environment's (including Windows), locking the screen is usually `Super + L`, however in Cinnamon this launches the Cinnamon debugger, Melange.

<a name="log-out-of-current-session"></a>
### Log Out of Current Session

    Ctrl + Alt + Delete

<a name="workspace-shortcuts"></a>
## Workspace Shortcuts

**NOTE**: You can have as many workspaces as you like. When the documentation refers to moving "left" or "right", it means referring to the workspace immediately to the left or right of your current workspace. For example, if you are currently on Workspace 3, moving to the left workspace would switch you to Workspace 2. Moving to the right would shift you to Workspace 4, etc.

<a name="switch-to-left-workspace"></a>
### Switch to left workspace

    Ctrl + Alt + Left Arrow

<a name="switch-to-right-workspace"></a>
### Switch to right workspace

    Ctrl + Alt + Right Arrow

<a name="send-current-window-to-left-workspace"></a>
### Send current window to left workspace

    Ctrl + Alt + Shift + Left

<a name="send-current-window-to-right-workspace"></a>
### Send current window to right workspace

    Ctrl + Alt + Shift + Right

<a name="launchers"></a>
## Launchers

<a name="launch-the-gnome-terminal"></a>
### Launch the GNOME Terminal

**NOTE**: This is different from launching the console terminal as this is still within the GUI. The GNOME Terminal can be moved around and minimized at will.

    Ctrl + Alt + T

<a name="launch-nemo-file-manager"></a>
### Launch Nemo File Manager

    Super + E

<a name="launch-the-menu-application-and-search-bar"></a>
### Launch the Menu Application and Search Bar

    Super

<a name="window-management"></a>
## Window Management

<a name="cycle-between-open-windows---applications"></a>
### Cycle between open windows / applications

To cycle from left to right, use:

    Alt + Tab

To cycle in the reverse direction, use:

    Alt + Shift + Tab

<a name="cycle-between-open-instances-of-the-same-application"></a>
### Cycle between open instances of the same application

By default `Alt + Tab` to cycle open windows will lump all instances of an application together. If you wish to cycle through those clumps of the same application (e.g. multiple File windows, multiple instances of Firefox, etc.), use the following command:

    Alt + Grave (`)

<a name="show-desktop"></a>
### Show Desktop

    Super + D

<a name="snap-current-window-to-left-side-of-screen"></a>
### Snap current window to left side of screen

    Super + Left

<a name="snap-current-window-to-right-side-of-screen"></a>
### Snap current window to right side of screen

    Super + Right

<a name="snap-current-window-to-top-of-screen"></a>
### Snap current window to top of screen

    Super + Up

<a name="snap-current-window-to-bottom-of-screen"></a>
### Snap current window to bottom of screen

<a name="screenshots"></a>
## Screenshots

<a name="take-a-screenshot"></a>
### Take a Screenshot

    Print / PrtScr

<a name="take-screenshot-of-the-current-window"></a>
### Take Screenshot of the Current Window

    Alt + PrtScr

<a name="take-screenshot-of-selected-area"></a>
### Take Screenshot of Selected Area

    Shift + Print

<a name="record-the-desktop"></a>
### Record the Desktop

    Shift + Ctrl + Alt + R
