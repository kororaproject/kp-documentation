**Table of Contents**  

- [How To Backup Your System](#how-to-backup-your-system)
    - [Why You Should Make a Backup](#why-you-should-make-a-backup)
    - [What to Backup](#what-to-backup)
    - [System Backup vs Personal Backup](#system-backup-vs-personal-backup)
    - [Backup vs Sync](#backup-vs-sync)
    - [Backup Best Practices](#backup-best-practices)
        - [Test Your Backup](#test-your-backup)
        - [Local and Off-Site Backups](#local-and-off-site-backups)
        - [3-2-1 Rule](#3-2-1-rule)
    - [Getting Started:  Included Programs](#getting-started--included-programs)
        - [Déjà Dup](#deja-dup)
        - [Back in Time](#back-in-time)
        - [Third-party or DIY Solution](#third-party-or-diy-solution)



<a name="how-to-backup-your-system"></a>
How To Backup Your System
=========================

<a name="why-you-should-make-a-backup"></a>
## Why You Should Make a Backup

A backup protects your files from data loss, malware infections, and inadvertent deletions. Storing your important files in a backup location allows you to restore those files to your computer should they ever be removed, go missing, or otherwise become corrupted.

<a name="what-to-backup"></a>
## What to Backup

Ideally, you should be backing up all personal files and directories that are important to you. Only you can know for sure what directories are important to you, but it goes without saying that files such as pictures downloaded from your camera may hold more sentimental value than, say, your internet browser's cache.

If you wish to try to preserve your application data, you may need to research where each individual app of interest tends to store its data. If your application follows standard conventions, it likely stores its settings somewhere in the user's home directory. So it may not be a bad idea to backup:
- ~/.config
- ~/.local
- /opt (If you wish to backup the application itself)
- /usr/local/share
- /etc

Be aware that within application directories there may also reside cache subdirectories that can probably be excluded in order to reduce the size of the backup.

**NOTE**: "~/" is an alias to the user's home directory. So if you are logged in as 'guest', ~/.config would evaluate to */home/guest/.config* by the system.

<a name="system-backup-vs-personal-backup"></a>
## System Backup vs Personal Backup

In order to figure out how best to backup your computer, you first need to decide what on your computer is important to you. For instance, imagine your computer stopped working tomorrow due to a hard-drive crash, and you had nothing backed up. Which of these goals is more relevant to you:
1. I don't care if I have to put in a new hard-drive and/or reinstall the OS, so long as I get my personal files (documents, pictures, movies, music, etc.) off the old drive first.
2. I need to get *this* hard-drive working again, because the operating system / applications / configurations on it are essential to my workflow.

There is no right or wrong answer. Some people are not particularly attached to their computer so long as they have all of their personal media available. Other people, perhaps power-users, might have configured their system in a very specific way and are not keen on re-doing it.

If you identified more with the first goal, you would likely prefer a **Personal/Media**-aimed backup. This means that you will primarily be backing up personal files like your documents, your pictures, your songs, etc. Most consumable media tends to be cross-platform, and so a backup of Documents, Pictures, and Music made on one version of Linux could easily carry over to another Linux flavor, or even to Windows and MacOS. 

If the second goal sounds more palatable to you (e.g. if your computer dying tomorrow means you can't work and your business or livelihood becomes threatened), then you may be more interested in pursuing a **System Backup**. A System Backup aims to preserve the bits that relate to the OS itself and keep it functional. This would allow you to easily revert the system if, say, a bad update suddenly makes your system unusable.

While a System-only backup is theoretically possible, it requires a *deep* understanding of the OS and its specific storage locations that most people do not have (include this article's author). In practice, a System Backup is usually performed as part of a Full Disk backup, sometimes called a Snapshot (the term "snapshot" is used heavily in virtualization software, where the snapshot represents the entire VM's disk and state at the time of the snapshot). In a Full Disk backup, the entire hard-drive is copied and imaged. If you need to revert to the backup, the image would be decompressed and applied back onto the drive. This would also allow you to replace the original drive with one of an identical size and then restore the image onto the new drive.

If your computer's continued operation and contents are mission critical, you may consider making the occasional Full Disk backup. You should be aware, however, that you should only restore such an image onto *similar if not identical* hardware. Because restoring an image skips the OS installation phase and other initial configuration, the OS running on the re-imaged disk will still be running under the assumption that it has the hardware it originally had; discrepancies between what it originally had and what it now has could cause problems. 

For example, let's say your original system lived on a 20GB hard-drive inside of a laptop with a single core processor and an integrated GPU. You make a Full Disk backup of the drive shortly before it dies. Because the whole thing is getting old, you decide to buy a new computer--a proper desktop tower with a 128GB SSD, a quad-core processor, and discrete GPU. But because you really liked the way you had everything setup on the old laptop, you decide to use the last backup you made and "restore" it to the new desktop's hard-drive. Right off the bat, you may run into the following problems:
+ The hard-drives are different sizes, so after restoring the original image to the new hard-drive, you have around 100 gigs of unallocated space. To make effective use of this space, you should consider then using a tool like `GParted` to either create new volumes or increase the existing volumes from the original image.
+ The drivers have not been installed or configured for your GPU video card yet, and so at a minimum, it will probably not be recognized by the OS and will be unusable at first. In the worst case scenario, you may get a black screen as soon as you get past the BIOS!
+ Other issues with hardware mismatches, such as the networking card, sound drivers, etc. may not work at the very least until the OS detects the new hardware and reconfigures itself.

<a name="backup-vs-sync"></a>
## Backup vs Sync

Sometimes when applications or app-makers talk about "backing up", they're really talking about "syncing". Backing Up means that File 1 is in Locations A, B, and C, and I can retrieve File 1 from Location B if Location A is destroyed. I can make *changes* to File 1 in Location A, and it will not affect the files at Locations B and C because they only contain the version of File 1 that existed when I made the copies. "Syncing" means that File 1 is in Locations A, B, and C, and any changes I make to File 1 at Location A get propagated to Locations B and C. Syncing is the idea behind something like Dropbox, which allows you to install the program on your computer, your phone, and your tablet, and have files seamlessly shared between all three, with changes made to File 1 on your phone then showing up instantly on your tablet and your computer. It has some advantages over a periodic, time-based backup, such as:
+ Many sync programs happen in real-time, so if your computer suddenly crashes while working on something, you get as close as possible to being able to pick up where you left off from the synced files.
+ Syncing works well for collaboration, when many people may be working on a file or folder.

However, it is **not** a backup, and has several shortcomings against a conventional backup. These include:
+ Any change that is made, good or bad, is immediately propagated to all locations. If I inadvertently delete a paragraph in File 1 and don't realize it until several hours later, after I've saved the file, that paragraph has already been deleted at Locations B and C's File 1 as well. There would be no way to get that paragraph back without (you guessed it) a backup.
+ Similarly, if File 1 is inadvertently deleted, it would be deleted from the other locations as well.
+ Syncing often forces the two ends of a synced file or directory to mirror each other when it is not desired. For example, you might have a 'Music' directory on a 1TB external hard-drive that holds all of your music, and a smaller 'Music' folder on your smartphone that only holds 8GB because of the storage limitations of the smartphone. If you attempted to "sync" the two directories, you might end up deleting all but 8 gigs on the external hard-drive because the sync would force both ends to mirror each other, and anything that was not on the smartphone's Music folder would be deleted from the external drive.

There are hybrid solutions that couple Sync with Version History (a kind of backup), so that at the very least if an erroneous change is made to File 1, you can restore it to an earlier version.

<a name="backup-best-practices"></a>
## Backup Best Practices

Below are some of best practices for managing and distributing your backups.

<a name="test-your-backup"></a>
### Test Your Backup

One mistake seen all too often is the real world is people checking the logs to see that their backup ran, but never **verifying** the backup itself. Don't trust the backup program itself to tell you that a backup was successful. You should periodically verify this for yourself by *restoring* one of your backups (to another location, if necessary) and confirming that the files are there. You don't want your first restoration to be during a crisis, only to discover then and there that your backups haven't been working as intended.

A simple way to test your backup is to find a file or folder that is being backed up and doing the following:

    mv test_file test_file.aside
    (command or series of commands to restore test_file from backup)
    diff test_file test_file.aside

In the first line, we rename/move a sample file out of the way so that the backup program thinks the file is missing.

In the second line, we restore that file from the backup to its original location. This is so that we know for sure that the test_file is the copy that came from the backup.

Finally, we use the `diff` command to compare the test file to the one retrieved from the backup.

If the backup program **cannot** restore the test file, or the test file and its backup **differ**, you have a problem, and need to take another look at your backup setup.

<a name="local-and-off-site-backups"></a>
### Local and Off-Site Backups

In IT, the term "Disaster Recovery" refers to mitigations and protections for data loss when a data center suffers some critical unforeseen event, such as a natural disaster flooding the data center. To protect against something like that, it is popular to keep both local and off-site backups. 

"Local" storage refer to data that is backed up on an easily accessible backup media, such as an external hard-drive or tape drive that is stored in your facility. "Off-site" storage refers to media that is stored in a remote location, so that if your house or office catches fire and both the original media and local backup are lost, a second backup exists elsewhere.

<a name="3-2-1-rule"></a>
### 3-2-1 Rule

The [3-2-1 rule](http://blog.trendmicro.com/trendlabs-security-intelligence/world-backup-day-the-3-2-1-rule/) is a backup recommendation that suggests:
- Make at least three copies of your data
- On at least two different mediums
- At least one of which should be off-site

By "mediums" we mean the storage medium for the data. Even three copies of a single folder of data, if they are all stored on the same spinning-disk hard-drive format, are not sufficiently resilient. Ideally, one of those backups should be on a read-only format like a CD/DVD/Blu-Ray. Another could be on something like flash memory. 

<a name="getting-started--included-programs"></a>
## Getting Started:  Included Programs

Korora aims to include a prepackaged backup application into the distro, regardless of which desktop you've chosen. If you are using a Gtk-based desktop (GNOME, Cinnamon, MATE, or Xfce), you will likely have Déjà Dup preinstalled. If you are on KDE, you will have Back in Time preinstalled.

<a name="deja-dup"></a>
### Déjà Dup

Déjà Dup is a GNOME-based frontend for the `duplicity` app, designed for quick and easy backups. You can read our page on [Déjà Dup](Deja-Dup.md) for more information.

<a name="back-in-time"></a>
### Back in Time

Back in Time is a Qt-based graphical backup application for KDE (although it can be installed on GNOME as well). You can read our page on [Back in Time](Back-In-Time.md) for more information.

<a name="third-party-or-diy-solution"></a>
### Third-party or DIY Solution

Other applications exist to cover your unique backup needs. Should the backup applications included with Korora not meet your needs, you are encouraged to check out others like [Borg](https://borgbackup.readthedocs.io/en/stable/), [rsnapshot](http://rsnapshot.org/), or [TimeShift](https://github.com/teejee2008/timeshift). TimeShift, in particular, may be of interest to people who are looking for a System Backup application without creating a full disk image.

You are also welcome to write your own backup scripts. Many backup tools are simply frontends and schedulers built on top of the amazing tool `rsync`. With sufficient knowledge of rsync and an off-site storage provider to dump your backups, it is not difficult to setup a few scripts to run rsync and copy off your data to different locations. 