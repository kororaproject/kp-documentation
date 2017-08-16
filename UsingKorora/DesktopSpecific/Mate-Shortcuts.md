# Mate Shortcuts
**Table of Contents**  

- [Changing the Defaults Shortcut Keybindings](#keybindings)
- [Emergency Shortcuts](#emergency)
    - [Launch a Console Terminal](#console)
    - [Restart Mate](#restart)
    - [Shut Down](#shutdown)
- [Session Shortcuts](#session)
    - [Lock Screen](#lock)
- [Workspace Shortcuts](#workspace)
    - [Switch to Left Workspace](#leftwork)
    - [Switch to Right Workspace](#rightwork)
    - [Send Current Window to Left Workspace](#sendleft)
    - [Send Current Window to Right Workspace](#sendright)
- [Open the Menu and Search bar](#menu)
- [Window Mangement](#wm)
    - [Cycle between Open Windows / Applcation](#cycle)
    - [Cycle between Open Windows of the Same Application](#cyclesame)
- [Screenshots](#screen)
    - [Take a Screenshot](#screenf)
    - [Take a Screenshot of the Current Window](#screenw)


    
The Mate desktop environment has a number of built-in shortcuts for manipulating the system's resolution, switching workspaces, and launching applications. Mastery of these shortcuts will greatly reduce the amount of time spent clicking around menus and potentially boost your productivity.

**NOTE**: We will not cover all of the available shortcuts. You can look at the Keyboard menu discussed below in order to see them all. This article will cover some of the ones you are most likely to use.

**NOTE on Key Terminology**:

 * If your keyboard came from a Mac, the `Alt` key might be labeled `Option` instead.
 * If your keyboard came from a Mac, you likely have a `Command` key. If you have a Windows-based keyboard, you likely have a Windows key. These keys are referred to in the Linux world as the `Super` key (or `Meta` key in emacs and a few other contexts)
 * The \` key is sometimes called the `grave` or `backtick`. It is usually found above the Tab key, and shares its key with the tilde (~).

## Changing the Default Shortcut Keybindings <a name="keybindings"></a>

We will be discussing the shortcuts as they exist on a freshly-installed instance of Korora Mate. However, if you would like to change the default shortcuts to better suit your keyboard or workflow, you are free to do so by opening the Keyboard settings application, which can be reached by navigating through the following menu path:

**Menu -> System -> Preferences -> Hardware -> Keyboard Shortcuts**

![keyboard-shortcuts](https://github.com/kororaproject/kp-documentation/wiki/img/mate-shortcuts.png?raw=true "Keyboard Shortcuts window") 

## Emergency Shortcuts <a name="emergency"></a>

### Launch a Console Terminal <a name="console"></a>

If Mate becomes unresponsive or you need to otherwise access a text-only console terminal outside of the window manager, enter the following command:

    Ctrl + Alt + F2

You can switch back to the GUI by hitting:

    Ctrl + Alt + F1

### Restart Mate <a name="restart"></a>

If Mate has become buggy or unusable, you can try restarting it via the following:

    Ctrl + Alt + Escape

### Shut Down <a name="shutdown"></a>

    Ctrl + Alt + Del

## Session Shortcuts <a name="session"></a>

### Lock Screen <a name="lock"></a>

    Ctrl + Alt + L

## Workspace Shortcuts <a name="workspace"></a>

**NOTE**: You can have as many workspaces as you like. When the documentation refers to moving "left" or "right", it means referring to the workspace immediately to the left or right of your current workspace. For example, if you are currently on Workspace 3, moving to the left workspace would switch you to Workspace 2. Moving to the right would shift you to Workspace 4, etc.

### Switch to left workspace <a name="leftwork"></a>

    Ctrl + Alt + Left Arrow

### Switch to right workspace <a name="rightwork"></a>

    Ctrl + Alt + Right Arrow

### Send current window to left workspace <a name="sendleft"></a>

    Ctrl + Alt + Shift + Left

### Send current window to right workspace <a name="sendright"></a>

    Ctrl + Alt + Shift + Right

## Launch the Menu Application and Search Bar <a name="menu"></a>

    Super

## Window Management <a name="wm"></a>

### Cycle between open windows / applications <a name="cycle"></a>

To cycle from left to right, use:

    Alt + Tab

To cycle in the reverse direction, use:

    Alt + Shift + Tab

### Cycle between open instances of the same application <a name="cyclesame"></a>

By default `Alt + Tab` to cycle open windows will lump all instances of an application together. If you wish to cycle through those clumps of the same application (e.g. multiple File windows, multiple instances of Firefox, etc.), use the following command:

    Alt + Grave (`)

## Screenshots <a name="screen"></a>

### Take a Screenshot <a name="screenf"></a>

    Print / PrtScr

### Take Screenshot of the Current Window <a name="screenw"></a>

    Alt + PrtScr
