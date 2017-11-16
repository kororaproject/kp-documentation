**Table of Contents**  

- [Dnfdragora](#dnfdragora)
    - [File Menu](#file)
    - [Options](#options)
    - [Software Management](#manage) 
- [Optional: Dnfdragora Updater](#updater)

![Dnfdragora](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-1.png?raw=true)


While there are some dedicated terminal line users who use the dnf package manager, today’s end user likes the graphical option for installing software. Gnome and KDE have dedicated software centers that fulfill this purpose. However the other DEs’ do not have have this feature. Dnfdragora provides a graphical frontend to the command line tool dnf and is cross platform compatible. Simply look into the administrative section of your DE's menu to find this program. 

<a name="dnfdragora"></a>
### Dnfdragora
Dnfdragora is divided into 2 programs, the updater and the program itself. The program is fairly user friendly and self-intuitive.  Simply review the various embedded menus into understand how dnfdragora fully works.  Let’s begin with reviewing the upper left embedded menus. The upper right corner has the Help menu. At this time the manual is not embedded.

<a name="file"></a>
#### File Menu
![File](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-3.png?raw=true)
File, which is on the upper left side, contains the following options: Reset the selection, Refresh Metadata, Repositories, and Quit. 

The first option will reset package selection e.g. if you select a number of packages to be installed this option will unselect them. 

Refresh Metadata checks for any metadata changes in the enabled repositories. 

![Repos](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-2.png?raw=true)
The enabled software repositories populate on the screen. The end user can enable various repositories here. The additional repositories are only enabled for the current session. 

Choosing the Quit option will close dnfdragora. 

<a name="options"></a>
#### Options
![Options](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-4.png?raw=true)
Options will populate the software behavior for the program. By default when dnfdragora starts it will query the repositories and check for needed updates.  Additionally you can have dnfdragora continue to scan for updates when needed while the OS is operating.

<a name="manage"></a>
#### Software Management
![Software Management](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-5.png?raw=true)
Under the Software Management header is the main areas of use. There are three menu options here: Groups, To update, and in names. These three menus are relational. With the correct sub menu choices it is possible to find the desired software. For example I want to install Leafpad. I would choose the Groups, All, and in names menu options. I would then enter text into search word bar looking for Leafpad and I would choose the Search button. The program will cache the the groups to find the program. (I suggest waiting for the caching groups from packages to be finalized before choosing the Search button.) Click the blank square next to the Name to activate a gray arrow. This gray arrow selects the program installation. Finally press the Apply button to install Leafpad. A new window populates the screen describing the transaction dependency. 
![Transaction](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-6.png?raw=true)
Simply click the OK button at the bottom, the Authenticate Box will then ask for the root password to enable the install. Simply that is a basic introduction to using dnfdragora.
![aunthenticate](https://github.com/kororaproject/kp-documentation/blob/master/img/DNG-Dragora-7.png?raw=true)

<a name="updater"></a>
### Optional: dnfdragora-updater
The updater is not included in Korora at this time due to some outstanding issues. One concerns resuming for Suspend and Hibernate, (see [here](https://github.com/manatools/dnfdragora/issues/45)). The other is issues when the default icon theme isn't used, see [here](https://github.com/manatools/dnfdragora/issues/55). Until these issues are solved we can't recommend it.

To install Dnfdragora-updater use the command `sudo dnf install dnfdragora-gui` or search for it in dnfdragora.

The dnfdragora-updater was developed after dnfdragora was created based off user requests. On my desktop the updater is a simple box that has four drop down options: Update, Open dnfdialog, Check for updates, and Exit.  You can think of these options as shortcut icons.

The Check for Updates will search for new software upgrades. Update will install the available upgrades. Open dnfdragora dialog opens the dnfdragora graphical utility. Exit will simply close the program.

