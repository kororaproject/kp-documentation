# Accessing a Text Console
## What is a Text Console?

Modern Linux systems use a Graphical User Interface (GUI) to interact with the user. However, there is still a non graphical or text user interface available. It provides direct access to the operating system without the desktop environment getting in the way.

While it is possible to work in a text console all the time you would normally only use it when there are problems that can't be fixed in a GUI or you can't get to a GUI.

## Accessing a Text Console

To enter a console hold down Control and Alt, then press F2 or F3 (there used to be more of these). It is just a method of navigating you around different desktops, F1 is the standard GUI screen and F2 & F3 are text consoles. All of them can be performing different tasks simultaneously and any user of any level can find them useful. You do not lose the GUI by switching to a console, a simple press of Ctrl + Alt + F1 will take you back.

> Beware though that F7 was also commonly used for the GUI and may still be in use on some distros.

<br />


>If you have a problem getting back to the GUI try using only the left Ctrl and Alt. During testing, on at least one machine, the right Ctrl and Alt keys worked in a GUI but not in a text console.

## Example of Using a Text Console

As an example to see what processes are running - What you do is: `Ctrl + Alt + F2` _You should be taken to a text console_.

Then type your username followed by your password, this is the same username and password you use to log in to the gui.

> Please be aware that no characters will appear when you type the password but you can still backspace if you think you made an error.

If greater permission is required e.g. to kill any process or install some packages you can use `sudo` or exit and log back in as `root`. This will make it less easy for an intruder to do damage.

Next: `top`

Top is a program (the program’s name is top in case of confusion) which will open in the console and show the currently running processes. It has excellent built in help (press h) to assist you to use it. It is very similar to Microsoft’s task manager, or one of several of the Linux GUI ones (most use top anyway).

To exit top type: `Ctrl + c`

To log off type: `exit`

Then type: `Ctrl + Alt + F1` and you should be in a working GUI

A text console works much like a terminal on your desktop which is more correctly called a virtual terminal. You can use many applications but not ones that require or depend on a GUI. For example you can use a text editor like nano but not a GUI one like Kwrite.
