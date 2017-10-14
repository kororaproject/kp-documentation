## Building ISOs with Canvas
Canvas is the application Korora team members use to build Korora ISOs and it is included in each Korora system. Building ISOs is only one of its functions but that is what is covered here. There are more details on Canvas on our [Github site](https://github.com/kororaproject/kp-canvas/tree/master/upstream/client).

### Why build
You may ask why would you build your own ISOs when Korora does that for you? There are a number of reasons but here are 3.

#### Up to Date ISOs
After Korora is released there are a constant series of package updates. While it is a good idea to update the system immediately after installation and keep it up to date, there is a better option. If you are installing a new Korora system you can use Canvas to build your own updated ISO which will then include all the latest packages.

#### Testing Pre-Release Versions
Before Korora is released the team build and test pre-release versions of the various ISOs. However for recent versions we haven't released beta versions for general testing. Now you can build a pre-release version and provide feedback before the final version is released. While pre-release versions are not recommneded for day to day use, the feedback provided will ensure the final released version is the best it can be.

<div class="callout callout-warning"><p>Pre-release versions may contain untested applications and may be based on beta releases. As such they are for testing purposes only and not recommneded for day to day use.</p></div>

#### Community Versions
One of the features of Canvas is that anyone can create a special version of Korora. It is anticipated that many people will share their creations. These may be desktop environments that Korora doesn't provide or special use systems such as gaming systems, media servers etc. There will be a library of community versions that you can choose from.

<div class="callout callout-warning"><p>The Korora team have not tested or approved community versions which may contain untested applications and may be based on beta releases. As such only limited support may be available for them.</p></div>

### Prepare Your System
First check you have the latest version of Canvas installed, `sudo dnf --refresh upgrade canvas`. There is only one extra package needed, livecd-tools. `sudo dnf install livecd-tools`.

### Buld Command
Systems are based on templates that Korora has prepared. To list the  available templates type `canvas template list`. This will show all the templates that you can use. The list will include any templates you have created and all public templates.

The command to create an ISO is 
```
sudo canvas template iso_name_of_chosen_template --releasever nn --livecd-creator
```
So e.g. the coomand to build Korora Xfce version 26 will be `sudocanvas template iso kororaproject:korora-live-xfce --releasever 26 --livecd-creator`

This process will take some time as it will download all the required packages and then assemble the ISO. You can follow the progress as it continues.

When the process is complete you will find the ISO in /var/tmp/canvas/template_of_your_choice/iso/. This ISO can be used just like any ISO downloaded from the Korora site.

### Support and Bug Reports on Canvas
If you have any questions on Canvas and building systems please feel free to ask on our irc channel or on [Engage](https://kororaproject.org/support/engage). 

Bug reports can filed  [here](https://github.com/kororaproject/kp-canvas/tree/master/upstream/client). Suggestoins and Pull Requests are always welcome.

### Feedback on Pre-Release Systems
Feedback such as suggestions, issues and ideas on the pre-release ISOs is appreciated and best provided on [Engage](https://kororaproject.org/support/engage).