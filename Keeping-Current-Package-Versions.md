# Keeping Current Package Versions

On occasion you may find it necessary to prevent a package from updating. This usually occurs when a new version introduces a serious bug or breaks backwards compatibility with your original data. It is possible to inhibit package updates for nominated packages while still updating the rest of your system.

This should not normally be a permanent setting but can be used until an update is available to fix to your bug or you've converted your data appropriately.

> It is recommended that you check that a bug report has been filed for the problem. If so add a comment to the report, if not please file one.

## With the Command Line

Until a fix is available you can block the offending package from updating by adding an option to the command, replace packagename with the name of the package(s), it can include characters such as `*`,

```
sudo dnf --refresh --exclude=packagename upgrade

```
## In Configuration Files

It is also possible to add the exclude option to the configuration file. If you use a gui update application this is the best option. It is a good idea to edit both the the Yum and DNF files. You will need root permission to edit this file so use `su -` or prefix the command with sudo. Add `exclude=packagename` to /etc/dnf/dnf.conf.

## Kernel Versions

If the problem package is the kernel there is a another and preferred option and that is to increase the number of kernels the system retains. This will allow the latest kernel to be tested but a kernel that is known to work is retained.

You will need to use `su - ` or run the editor with sudo. Increase the setting on the `installonly_limit=` line in /etc/dnf/dnf.conf. A setting of 4 or 5 is usually sufficient.
