<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Installing Oracle's Java](#installing-oracles-java)
  - [Download Java](#download-java)
  - [Slotting Java](#slotting-java)
  - [Test Java](#test-java)
  - [Updating Java](#updating-java)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Installing Oracle's Java

One of the things that Oracle did after it pried Java from Sun's cold dead hands was to change the license so that no Linux distributions could distribute it any more.

By default, Korora comes with the OpenJDK version of Java and you probably don't want to uninstall it because some applications depend on it. You can see the OpenJDK version when you query Java.

```
 java -version
```
In order to install Oracle's Java it must be done manually, but fortunately it's not too difficult thanks to the way Java can be slotted (multiple versions installed) on Linux.

## Download Java

Head over to the [Java download page](http://www.oracle.com/technetwork/java/javase/downloads/index.html) and select either the JRE (runtime environment) or the JDK (development kit) of the SE (standard edition).

![](https://github.com/kororaproject/kp-documentation/blob/master/img/install-oracle-java-download.jpg)

At the download page, agree to the license and then download the RPM for your architecture (64 bit JDK in the example below) and save it somewhere like your Downloads directory.

![](https://github.com/kororaproject/kp-documentation/blob/master/img/install-oracle-java-select.jpg)

In our example, the file we downloaded is called _jdk-7u51-linux-x64.rpm _ however yours will most certainly be different so substitute as appropriate.
Install Java

You can install this RPM using a graphical package manager if you like, however we also need to use the command line to configure the slotting so let's do it all there instead.

Open up a terminal program, such as Konsole in KDE, and install the RPM which should end with Complete! message.

```
sudo yum install ~/Downloads/jdk-7u51-linux-x64.rpm
```

Now that we have Oracle's Java installed you can see where this was installed to by running the following command.

```
rpm -ql jdk
```

Or if you're installing the jre, this.

```
rpm -ql jre
```

You will note that Java was installed to_ /usr/java/_ however the RPM also creates a symbolic link so that _/usr/java/latest _ always points to the version you have installed. That's great because we can use that when configuring our slotting and if you upgrade the RPM in the future you will automatically be running the latest version!

## Slotting Java

To add that new Java to the list of slotted versions we use the alternatives command. This looks complicated, but it's installing another option for the_ /usr/bin/java_ executable (called java) which is at _/usr/java/latest/bin/java_ (where the RPM installed Java to). The number on the end sets the priority over any other java binaries (the highest number wins) when using alternatives in an automatic state (we will use manual).

```
sudo /usr/sbin/alternatives --install /usr/bin/java java /usr/java/latest/bin/java 999999
```

Now, we can select this version of Java to use as our default! Simpy run this command and select the number that corresponds with the _/usr/java/latest/bin/java_ entry.

```
sudo /usr/sbin/alternatives --config java
```

If you installed the JDK you can also do the same for _javac_, the Java compiler.

```
sudo /usr/sbin/alternatives --install /usr/bin/javac javac /usr/java/latest/bin/javac 999999
sudo /usr/sbin/alternatives --config javac
```

## Test Java

Test that you're running the right version with the same version command we ran at the beginning when only OpenJDK was installed.




Note that you shouldn't see OpenJDK any more, but something like Java(TM) SE Runtime Environment along with the version you installed!

## Updating Java

Unfortunately this is also a manual process, however now that you've already configured the slotting to use the latest symlink you can simply download and install the latest Java RPM as above.

Enjoy!
