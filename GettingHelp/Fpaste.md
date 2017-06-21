

**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [fpaste a file](#fpaste-a-file)
- [fpaste the output of a command](#fpaste-the-output-of-a-command)
- [fpaste with copied text](#fpaste-with-copied-text)
- [Other Options](#other-options)



When seeking support it is often useful to share the contents of a configuration file or the output of a command. Korora has a builtin utility for doing exactly this. It is fpaste. 

Fpaste makes use of the fpaste.org pastebin service.

Using fpaste is simple. You run fpaste from the command line point it to the text and it gives you a url which you can share with those offering support. How you provide the text to fpaste depends on the source of that text. 

Note: there can be a short delay while fpaste uploads your text and receives the url. the length of that delay will depend on the speed of your internet connection and the amount of text involved.

### fpaste a file
If the text is the contents of a file, e.g. a configuration file, you can simply type `fpaste filename`.  E.g. to share your bash configuration file you would type `fpaste ~/.bashrc` and fpaste would return the url.

### fpaste the output of a command
If you are sharing the output from a command the format is `command | fpaste`. E.g. to share the details of your graphics card type `/sbin/lspci | grep -e VGA | fpaste`. 
Note: it is a good idea to run the command without fpaste first so you can see the information you are sharing and to confirm the output contains the required information.

### fpaste with copied text
If you wish to share some text you can simply copy it and paste it into fpaste. To do this run `fpaste` without any options, paste the test, press enter and then Ctrl + D.

A short cut for this is `fpaste -io`. This will copy to selection in the primary clipboard to fpaste and return the url there. You can then paste the url in the support request.

### Other Options
There are plenty of other ways to use fpaste, those above are just cover most situations. To see the other option run `man fpaste` or `fpaste -h`.
