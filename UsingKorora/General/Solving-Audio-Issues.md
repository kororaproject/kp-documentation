

**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Solving Audio Issues](#solving-audio-issues)



# Solving Audio Issues

Most audio issues are easily solved using the installed tools in Korora. Common audio issues include no sound and sound not playing on the desired output device. The included tools include the PulseAudio Volume Control which is used to solve most issues. Also included are the command line Alsamixer and possibly a desktop environment’s own mixer. However these are rarely needed.

Occasionally audio applications may provide their own audio controls so check the application settings and if possible also test with another application. If the issue is limited to a single application try running it from a terminal and watch for error messages.

When there is any audio issue the first thing to check is that the correct output is selected. Then check that it isn’t muted. These are set on the Configuration and Output tabs of PulseAudio Volume Control.

There may be a panel plugin that controls this but it will just be a front end for the PulseAudio Volume Control which you will find on the Multimedia section of the menu. See here for more information on [PulseAudio Volume Control](https://github.com/kororaproject/kp-documentation/wiki/Pulse-Audio).

If you have a different issue or can’t solve your issue please ask on [Engage](https://kororaproject.org/support/engage).
