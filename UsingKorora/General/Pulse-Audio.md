

**Table of Contents**  

- [PulseAudio Volume Control (pavucontrol)](#pulseaudio-volume-control-pavucontrol)
    - [Configuration Tab](#configuration-tab)
    - [Output Devices](#output-devices)
    - [Input Devices](#input-devices)
    - [Recording and Playback Tabs](#recording-and-playback-tabs)



<a name="pulseaudio-volume-control-pauvcontrol"></a>
# PulseAudio Volume Control (pavucontrol)

This application is the most important tool for controlling the audio performance of your system. It sets the devices used, the output and input settings, per application settings as well as the volume.

Pavucontrol has several tabs to separate the various functions and it is worth taking a few minutes to explore the settings on each tab. In order from left to right they are Playback, Recording, Output Devices, Input Devices and Configuration.

>Hint. You may need to click on the left and right arrows to see all the tabs.

<a name="configuration-tab"></a>
## Configuration Tab
The Configuration Tab shows the various audio devices on the system. Most systems will show built in Digital and analogue option here. If you have other devices such as an external USB Audio card that will also appear. The defaults will be the best option in most cases.

<a name="output-devices"></a>
## Output Devices
The Output Devices is probably the most used tab as it shows the available outputs and the volume settings for those devices. The built-in analogue stereo output is usually used for the built-in speakers and headphone socket. Most systems will automatically switch to headphones when there are plugged in. Hint. Older external speakers used the headphone socket and so may appear as headphones when connected.

There is a slider to set the volume for each output. On the right side of the device title are 3 buttons. The first is the mute control. When selected the volume slider will be greyed out.

The second button locks the channels together. Unless you need to adjust the channel output separately this button isn’t needed and should be left in the default selected condition. The third button allows you to select one output as the fallback. If you select a particular device as the output for one application and it isn’t available this is the device that will play the sound. This is much like selecting a default output.

<a name="input-devices"></a>
## Input Devices
The Input devices tab works exactly lie the Output Devices but controls recording devices such as microphones and line in.

<a name="recording-and-playback-tabs"></a>
## Recording and Playback Tabs
We can look at these together as they function in the same way. Any application that is playing or recording audio will appear in the appropriate tab. An application will only appear while it is actually functioning. That is an application will not appear until it is outputting or recording audio. Just having an application open will not cause it to appear. The name of the application is shown and to the right of that is shown the device it is using. By clicking on the device you can select an alternative device. Below that is a volume level. Using that it is possible to have different applications output audio at different volume levels. There is one difference between the Playback and Recording tabs. On the playback tabs there is a permanent listing for system sounds. You can’t select the output device but you can set the volume or mute the System sounds.
