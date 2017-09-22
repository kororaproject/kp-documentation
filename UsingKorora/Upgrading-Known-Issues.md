

**Table of Contents**  

- [Upgrading - Known issues](#upgrading---known-issues)
    - [Package Errors](#package-errors)
    - [User Installed Applications](#user-installed-applications)
    - [Third party Repos](#third-party-repos)
    - [Xfce Settings](#xfce-settings)



<a name="upgrading---known-issues"></a>
# Upgrading - Known issues

Using the upgrade facility is a simple way to move to Korora 26 without the need of a full installation. Your data, settings and installed applications are still there and you can keep working on your system for much of the process. There are a few known issues that may appear during the process, although they are all easily handled and the upgrade process should then proceed as expected.

There are some known upgrade issues reported on the [F26 known bugs list](https://fedoraproject.org/wiki/Common_F26_bugs#Upgrade_issues).

<a name="package-issues"></a>
## Package Issues

There are no reported package issues at this stage. However as Yumex-dnf is no longer developed it is recommended that Yumex-dnf be replaced with dnfdragora.

```bash
sudo dnf remove yumex-dnf

sudo dnf install dnfdragora
```

<a name="user-installed-applications"></a>
## User Installed Applications

Another issue that has affected a small number of people is the existence of applications installed outside of the package manager. These are usually built from source after installing the required dependencies. As those dependencies may have been updated these applications may not run or may give errors. It is advisable to re-build and or re-install these applications using the same process as employed originally. This is a good opportunity to check if they have been updated and to install the latest version.

<a name="third-party-repos"></a>
## Third party Repos

Similarly any non-standard or third party repos that have been added to the system may need to be disabled. If you see any errors connected with packages installed from those repos remove the packages and disable the repos. After the upgrade is complete the repos can be re-enabled if they have support for 26 and the packages can be installed.

<a name="other"></a>
## Other Issues
If you experience any issues not listed here please let us know on irc or on [Engage](https://kororaproject.org/support/engage).
