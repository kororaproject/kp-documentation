**Table of Contents**

- [How to Backup with Déjà Dup](#how-to-backup-with-d%C3%A9j%C3%A0-dup)
    - [Installing Déjà Dup](#installing-d%C3%A9j%C3%A0-dup)
    - [Making a Backup](#making-a-backup)
    - [Choosing a Storage Location](#choosing-a-storage-location)
    - [Scheduling a Backup to Run Automatically](#scheduling-a-backup-to-run-automatically)
        - [Frequency](#frequency)
        - [Number of Backups to Retain](#number-of-backups-to-retain)
        - [Scheduling Your Own Backup](#scheduling-your-own-backup)
    - [Restoring Files via Déjà Dup](#restoring-files-via-d%C3%A9j%C3%A0-dup)
        - [Restoring an Individual File](#restoring-an-individual-file)
        - [Restoring a Directory](#restoring-a-directory)
    - [Making Multiple Backups](#making-multiple-backups)
    - [Summary](#summary)


<a name="how-to-backup-with-d%C3%A9j%C3%A0-dup"></a>
How to Backup with Déjà Dup
============================

Déjà Dup is a simple backup program that should be bundled with most versions of Korora. It will allow you to save copies of your important files, applications, or system settings to a secondary location, where they can be restored if something should happen to your primary computer.

<a name="installing-d%C3%A9j%C3%A0-dup"></a>
### Installing Déjà Dup
Déjà Dup is preinstalled on the following Korora desktops:
- GNOME
- Cinnamon

If you need to install it on KDE, XFCE, or Mate, you can either grab the deja-dup package from Yumex/dnfdragora, or install it manually from a terminal by typing the following command:

    dnf install deja-dup    

When installed, the application will show up in the Menu under **Menu -> Accessories -> Backups**. 

![deja-dup location](../../img/DejaDup-Backups-In-Menu.png?raw=true "Déjà Dup Menu location")

You can still search for the app "deja-dup", and Backups will show in the results.

![deja-dup search](../../img/DejaDup-Backups-In-Search.png?raw=true "Déjà Dup Search results")

<a name="making-a-backup"></a>
## Making a Backup

Launch Déjà Dup / Backups. If you have not launched it before, you will need to configure what directories to include by clicking the "Folders to save" tab. By default, the current user's Home directory will be included.

![folders to save](../../img/DejaDup-Folders-To-Save.png?raw=true "Selecting which directories to backup")

Click the tab "Folders to ignore" and add any subdirectories within your Saved folders that you want Déjà Dup to skip.

![folders to ignore](../../img/DejaDup-Folders-To-Ignore.png?raw=true "Selecting which directories to ignore")

**NOTE**: Since many subdirectories that you may wish to add to the Save or Ignore pile are hidden, you may not be able to see them inside your File Manager program with the default settings. Should that happen, when you are presented with the prompt to Choose Folders pop-out menu, right-click the menu and check the box "Show Hidden Files". 

![show hidden files](../../img/DejaDup-Show-Hidden-Files.png?raw=true "How to display hidden files in the file selection screen")

<a name="choosing-a-storage-location"></a>
## Choosing a Storage Location

Select the tab "Storage Location" to choose where you wish for the backups to go. You have a couple of options that deja dup supports natively, such as:
- Local Folder
- A remote FTP or SSH directory
- WebDAV
- Amazon S3 instance
- Google Cloud Storage

For those non-local directories that require authentication, you will be prompted for a username and password.

*NOTE*: It is **highly recommended** that you not backup your files to the same location as their originals. Meaning, if you are backing up your local directories to somewhere else on the same hard disk, you have not created a very reliable backup. If your hard drive crashes, you would lose both the orignials and the backups! Leverage off-site storage if you can. At the very least, a backup to an external flash drive or hard-drive is advisable.

<a name="scheduling-a-backup-to-run-automatically"></a>
## Scheduling a Backup to Run Automatically

If you do not wish to run the backup manually each time, Déjà Dup contains settings for scheduling a cron job to run backups automatically for you.

To schedule a backup, open Déjà Dup and click on the "Scheduling" tab. 

![scheduling menu](../../img/DejaDup-Scheduling-Menu.png?raw=true "The backup scheduling menu")

By default, scheduling will be turned off. To turn it on, click the slider next to "Automatic backup" to push it to the right. Doing so will launch the Déjà Dup service and run Déjà Dup automatically at the appointed times. This same switch also appears on the title bar at the top-right corner, next to the window buttons (e.g. Minimize, Maximize, Close, depending on what you have).

When the scheduling function has been enabled, you will then be able to modify the backup schedule's frequency, and the age of the backups that are retained before being deleted.

![scheduling frequency](../../img/DejaDup-Schedule-Frequency.png?raw=true "Scheduling backup frequency and retention age")

<a name="frequency"></a>
### Frequency

Under the "Every" field option, you can determine how frequently the backup should run. Within the deja dup GUI, your options are somewhat limited:  you can select "Week" to run once a week, or "Day" to run every day. You are unable to choose on what day or at what time the backup will take place. According to Déjà Dup's [documentation](https://wiki.gnome.org/Apps/DejaDup/HowItWorks), the schedule monitor will "intelligently" figure out when to run the backup based on when you are logged in and when the system was last backed up.

<a name="number-of-backups-to-retain"></a>
### Number of Backups to Retain

Under the "Keep" field option, you can determine how many backup versions to keep before Déjà Dup will delete them in order to save space. Selecting the option "Forever" will instruct Déjà Dup that it should keep all backup files indefinitely and never delete them. Setting the field to "At least six months" will instruct Déjà Dup that it should not prune out any old backups unless they are over six months old. "At least a year" will extend the retention period to one year--you will not have any backups pruned unless they are over a year old.

When either of the options other than "Forever" are set, Déjà Dup will look at the age of the backups when it runs and figure out whether it can safely delete some old files. Per the [documentation](https://wiki.gnome.org/Apps/DejaDup/HowItWorks), the pruning/deletion of old backups is not instant or automatic. The program will first determine whether:
- Your system has at least two full backups *excluding* the one it wants to delete
- It can delete the old backup as part of a complete back chain (meaning a full backup and all of its associated incremental backups)

<a name="scheduling-your-own-backup"></a>
### Scheduling Your Own Backup

The GUI is currently limited in when it can be scheduled. Your personal backup needs may be more complex than what is available. For instance, you may wish to have a backup that runs:
- Only on Sundays
- At 3 AM, when you are not using your computer.

In which case, you may not be able to use the schedule monitor. However, you have the option of scheduling your own backups via the system cron. The following command, when run from the command-line, will start the backup process instantly in the background:

    deja-dup --backup

Since this can be run on a terminal and without the user's input, we can easily schedule this into a cronjob. To do that, you'll need to review (or learn) [cron syntax](https://en.wikipedia.org/wiki/Cron). If you need help, you can use something like the this [crontab generator](https://crontab-generator.org/) to generate the syntax for you. So, to have the backup run at 3AM on Sunday should give us something like the following:

    * 3 * * 0 /usr/bin/deja-dup --backup >/dev/null 2>&1

Now we just need to put it into the user's cron. To do this, enter the following command in the terminal:

    crontab -e

This will open the user's crontab in your default $EDITOR (most likely `vim` or possibly `nano`). Copy and paste the syntax you generated earlier somewhere into the cron, then save and quit. You can confirm whether it saved successfully by issuing the following command:

    crontab -l

It should then echo back to the console the user's installed crontab. If you see the entry for deja-dup, you are all set.

<a name="restoring-files-via-d%C3%A9j%C3%A0-dup"></a>
## Restoring Files via Déjà Dup

If your file manager does not support direct integration with Déjà Dup, you can use the deja-dup command discussed further below from the command-line to manually restore files.

<a name="restoring-an-individual-file"></a>
### Restoring an Individual File

To restore or revert an individual file using Déjà Dup, right-click on the file and select `Revert to Previous Version...`:

![revert from backup](../../img/DejaDup-Revert-From-GUI.png?raw=true "Restoring a file to an earlier version found in the backups")

If that option is not available in your File Manager, enter the following command in the terminal:

    deja-dup --restore /path/to/file

<a name="restoring-a-directory"></a>
### Restoring a Directory

To restore a directory of all missing files via Déjà Dup, open the directory in question and right-click anywhere inside the folder. Then select the option `Restore Missing Files...`:
![restore missing files](../../img/DejaDup-Restore-Missing-From-GUI.png?raw=true "Restoring any missing files in a directory found in the backups")

If that option is not available in your File Manager, enter the following command in the terminal:


    deja-dup --restore-missing /path/to/dir

<a name="making-multiple-backups"></a>
## Making Multiple Backups

As recommended by the [3-2-1 rule](http://blog.trendmicro.com/trendlabs-security-intelligence/world-backup-day-the-3-2-1-rule/), you should have multiple backups *in different locations*, and **at least one** should be off-site. Unfortunately, the Déjà Dup GUI does not allow multiple backup locations or profiles, and as of yet there is no way around this. The feature has been [requested](https://bugs.launchpad.net/deja-dup/+bug/324631) but remains unimplemented at this time.

One way around this is to change the storage location before running the backup. For instance, if you normally backup to an off-site Amazon S3 server, you could plug in a flash drive or external hard-drive, change the Storage Location to the external drive, and run the backup on the external drive once a month. The first time it runs, it would take awhile (because this would be a fresh, full backup on the new device), but the following month when you point the storage to the external drive again, the backup would be incremental and faster. When you are done, revert the Storage Location to the off-site S3 server. The backup destination directory contains information about when it last ran and can determine what has changed since then, and so you should be able to backup to two, mutually exclusive directories that will only keep track of their own backup history without contaminating the other.

Do not be afraid of using another backup solution **in addition to** Déjà Dup. If you are using Déjà Dup to backup your files to an external hard-drive, don't be afraid of manually uploading them to OneDrive/Google Drive/Dropbox, either, just to have an off-site solution. It needn't be through the provided software. You might try pairing Déjà Dup with something like [TimeShift](https://github.com/teejee2008/timeshift) to let the former handle your personal files, while letting the latter handle the system snapshots.

<a name="summary"></a>
## Summary

We have covered how to install and configure Déjà Dup for a quick-and-dirty, no-hassle backup solution. 

Key points to remember:
- Déjà Dup should be preinstalled on all versions of Korora except KDE, where BackInTime is preferred.
- Déjà Dup's default backup settings may be too broad for your use-case, so configure the Folders to Save and Folders to Ignore before running.
- If you don't like running backups manually, you can use the scheduler to have the backups run automatically
- Déjà Dup has some shortcomings that cannot be fixed within the GUI. See the sections on manually scheduling backups via the cron or backing up to multiple locations if those are of concern to you.