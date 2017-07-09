# Xfce Shortcuts
**Table of Contents**  

- [Changing the Defaults Shortcut Keybindings](#keybindings)
- [Emergency Shortcuts](#emergency)
    - [Launch a Console Terminal](#console)
- [Session Shortcuts](#session)
    - [Lock Screen](#lock)
    - [Log Out of the Current Session](#logout)
- [Open the Whisker Menu and Search bar](#whisker)
- [Screenshots](#screen)
    - [Take a Screenshot](#screenf)
    - [Take a Screenshot of the Current Window](#screenw)
- [Window Management](#wm)
    - [Cycle between Open Windows / Applications](#cycle)
    - [Show Desktop](#show)
- [Workspace Shortcuts](#workspace)
    - [Switch to Left Workspace](#leftwork)
    - [Switch to Right Workspace](#rightwork)
    - [Send Current Window to Previous Workspace](#prevwork)
    - [Send Current Window to Next Workspace](#nextwork)

The Xfce desktop environment has a number of built-in shortcuts for manipulating the system, switching workspaces and launching applications. Mastery of these shortcuts will greatly reduce the amount of time spent clicking around menus and potentially boost your productivity.

**NOTE**: We will not cover all of the available shortcuts. You can look at the Keyboard menu discussed below in order to see them all. This article will cover some of the ones you are most likely to use.

**NOTE on Key Terminology**:

 * If your keyboard came from a Mac, the `Alt` key might be labeled `Option` instead.
 * If your keyboard came from a Mac, you likely have a `Command` key. If you have a Windows-based keyboard, you likely have a Windows key. These keys are referred to in the Linux world as the `Super` key (or `Meta` key in emacs and a few other contexts)
 * The \` key is sometimes called the `grave` or `backtick`. It is usually found above the Tab key, and shares its key with the tilde (~).
 
 **NOTE on Super Key in Xfce**:
 One of the special features of Korora Xfce is the inclusion of Ksuperkey. This allows the Super key to be used as a shortcut by itself as well as to be used as part of a combination shortcut.

## Changing the Default Shortcut Keybindings <a name="keybindings"></a>

We will be discussing the shortcuts as they exist on a freshly-installed instance of Korora Xfce. However, if you would like to change the default shortcuts to better suit your keyboard or workflow, you are free to do so by opening the Keyboard settings application, which can be reached by navigating through the following menu paths:
**Menu -> Settings -> Keyboard -> Application Shortcuts** for Application and Session Shortcuts

![keyboard-shortcuts](https://github.com/kororaproject/kp-documentation/blob/master/img/Xfce-Shortcuts-apps.png "apps Shortcuts window") 

or

**Menu -> Settings -> Window Manager -> Keyboard** for Window Mangement and Workspace shortcuts

![keyboard-shortcuts](https://github.com/kororaproject/kp-documentation/blob/master/img/Xfce-Shortcuts-wm.png "WM Shortcuts window") 

## Emergency Shortcuts <a name="emergency"></a>

### Launch a Console Terminal <a name="console"></a>

If Xfce becomes unresponsive or you need to otherwise access a text-only console terminal outside of the window manager, enter the following command:

    Ctrl + Alt + F2

You can switch back to the GUI by hitting:

    Ctrl + Alt + F1

## Session Shortcuts <a name="session"></a>

### Lock Screen <a name="lock"></a>

    Ctrl + Alt + Del

### Log Out of Current Session <a name="logout"></a>

    Ctrl + Alt + L

## Open the Whisker Menu and Search Bar <a name="whisker"></a>

    Super
**Note:** the keyboard shortcut menu shows this shortcut as Alt + F1. This is part of the setup of Ksuperkey which makes the Super key more useful.

## Screenshots <a name="screen"></a>

### Take a Screenshot <a name="screenf"></a>

    Print / PrtScr

### Take a Screenshot of the Current Window <a name="screenw"></a>

    Alt + PrtScr
    
## Window Management <a name="wm"></a>

### Cycle between open windows / applications <a name="cycle"></a>

To cycle from left to right, use:

    Alt + Tab

To cycle in the reverse direction, use:

    Alt + Shift + Tab

**NOTE**: Xfce 4.12 added an option to have a preview of the Window instead of an icon when using ALT-Tab to cycle windows. The option uses the compositor so will only work when Compositing is on. This option can be turned off in Settings – Window Manager Tweaks – Compositing.

### Show Desktop <a name="show"></a>

    Ctrl + Alt + D
    
## Workspace Shortcuts <a name="workspace"></a>

**NOTE**: You can have as many workspaces as you like. When the documentation refers to moving "left" or "right", it means referring to the workspace immediately to the left or right of your current workspace. For example, if you are currently on Workspace 3, moving to the left workspace would switch you to Workspace 2. Moving to the right would shift you to Workspace 4, etc.

### Switch to left workspace <a name="leftwork"></a>

    Ctrl + Alt + Left Arrow

### Switch to right workspace <a name="rightwork"></a>

    Ctrl + Alt + Right Arrow

### Send current window to previous workspace <a name="prevwork"></a>

    Ctrl + Alt + Home

### Send current window to next workspace <a name="nextwork"></a>

    Ctrl + Alt + End
    
