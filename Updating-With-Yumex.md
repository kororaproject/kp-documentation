# Updating with Yumex

The Yum Extender, aka Yumex, is included with all versions of Korora because it provides a consistent interface across all desktops. Yumex is the most popular GUI for package management and is the default graphical Package Manager in Xfce and Cinnamon.

> Yumex is no longer under development. See [this news item ](https://kororaproject.org/about/news/new-gui-package-manager)for more information.

Using Yumex to update the system is simple as it checks for updates automatically whenever it is opened. Allow it to complete its check and display any updates.

If Yumex finds some updates it will list all that are available along with some information for each package. You can click on a package and the lower panel will show a description and other details of the package. The icons on the right side of the lower panel give access to additional information including package changes.

To apply the updates click “Select All” and you will see each line is selected. Next click “Apply”. Yumex will ask you for authentication, simple enter the requested password (which may be root's or your own if you are an administrator).

Yumex will take over and show its progress as it gets package information and checks for dependencies. When it is ready to proceed it shows a “Transaction Result” which details everything it will do. It shows the packages to be updated, dependencies to be added and possibly unneeded packages that will be removed. To proceed click “Okay”.

Yumex shows the progress of the update, a pop-up shows a summary while the main Yumex window in the background shows the details of each step. When it finishes Yumex will show its main window, which you can close now.

> If the update included a new kernel or other major system package you should reboot the system. If a new version of your desktop environment has been provided you should log out and back in.
