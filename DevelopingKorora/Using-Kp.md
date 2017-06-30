

**Table of Contents**  

- [Using the Korora Packaging tool, kp](#using-the-korora-packaging-tool-kp)
    - [Requirements](#requirements)
    - [Add user to the mock group](#add-user-to-the-mock-group)
    - [Creating a ssh key and adding it to your Git account](#creating-a-ssh-key-and-adding-it-to-your-git-account)
    - [SSH preparation](#ssh-preparation)
    - [Get code and setup](#get-code-and-setup)
    - [Checkout a version](#checkout-a-version)
    - [Sync the package list](#sync-the-package-list)
    - [Build first packages](#build-first-packages)
    - [Create a dnf repository](#create-a-dnf-repository)
    - [Build all packages](#build-all-packages)
    - [Create final repository](#create-final-repository)
    - [Create an image](#create-an-image)
    - [Boot your image](#boot-your-image)



<a name="using-the-korora-packaging-tool-kp"></a>
# Using the Korora Packaging tool, kp

Korora Package tool (called _kp_) is a bunch of shell scripts that wrap standard system commands (like git, mock and livecd-creator) to build Korora packages and images. Users should be running Korora or Fedora already, however which specific version generally doesn't matter.

Our code lives on GitHub, however you don't need an account in order to build packages as everything is publicly available. Building the packages and images is local to your machine, however if you wish to contribute fixes, please sign up for an account (you can use this to also log into Engage). You will then have read-only access to the Korora repositories over SSH protocol, but can fork our code and commit changes to your own repositories, then send us a pull request! :-)

<a name="requirements"></a>
## Requirements

Before we start setting up kp we need to install a few packages that are important and necessary to build our packages and live-iso later on.

```
sudo dnf install createrepo livecd-tools mock pykickstart rpm-sign

```

<a name="add-user-to-the-mock-group"></a>
## Add user to the mock group

Add yourself as user to the mock group. You replace {USER} with your own user name.

```
sudo usermod -a -G mock ${USER} && newgrp mock
```

<a name="creating-a-ssh-key-and-adding-it-to-your-git-account"></a>
## Creating a ssh key and adding it to your Git account

Simply follow the guide in this link on how to create a ssh key and add it to your Git account: [https://help.github.com/articles/generating-ssh-keys](https://help.github.com/articles/generating-ssh-keys/)

<a name="ssh-preparation"></a>
## SSH preparation

If you're using SSH, then set up the ssh-agent to cache your passphrase (if you use one)

```
eval $(ssh-agent &)
ssh-add
```

<a name="get-code-and-setup"></a>
## Get code and setup

Make a directory somewhere to put the Korora kp code:

```
mkdir -p ~/code/korora
cd ~/code/korora
```

Get the code:

>Developers should use ssh instead of https, git@github.com:kororaproject/kp.git

```
git clone https://github.com/kororaproject/kp.git
cd kp
```

Create your config file from the example config (it should work out of the box):

Developers should set the protocol to GIT_PROTOCOL="ssh" and set their KP_DEV_ACCOUNT and KP_DEV_EMAIL details.

```
cp kp.conf.example kp.conf
```

Initialise your kp directories:

>This creates the skeleton directory structure under ~/code/korora/kp/build/{conf,log,packages,release,repository}

```
./kp init
```

<a name="checkout-a-version"></a>
## Checkout a version

Checkout a revision, master defaults to the current release, else specify a branch like k21 for a previous release:

>This clones the config repository for each available package ~/code/korora/kp/build/packages

```
./kp checkout  --release master
```

<a name="sync-the-package-list"></a>
## Sync the package list

Next, sync down the packages repository, which will let kp know about available packages:

>This clones the kp-config repository to ~/code/korora/kp/build/conf

```
./kp sync
```

<a name="build-first-packages"></a>
## Build first packages

To build packages, we need to put our machine temporarily into SELinux permissive mode:

```
sudo setenforce  0
```

Build core packages (binary and source), korora-release and korora-repos:

>This creates packages under ~/code/korora/kp/build/repository/23/{source,x86_64}/

>Note that we are building these against Fedora, as we do not yet have the required local Korora repository

```
./kp build --arch x86_64 --releasever 23 --distribution fedora korora-release korora-repos
```

<a name="create-a-dnf-repository"></a>
## Create a dnf repository

Turn the directories with your packages into usable dnf repositories, which we will then use to build the remaining packages:

>kp can sign your rpms if you specify a GPG key in your config file, however by default we will not (--no-sign option)

```
./kp repository --releasever 23 --no-sign
```

<a name="build-all-packages"></a>
## Build all packages

Build the remaining packages, using your new korora repository as the base:

```
./kp build --arch x86_64 --releasever 23 --distribution korora
```

<a name="create-final-repository"></a>
## Create final repository

Re-build dnf repository with all the new packages:


```
./kp repository --releasever 23
```


<a name="create-an-image"></a>
## Create an image

Create a live image:

>This must be run as root and will create the ISO image in your kp dir ~/code/korora/kp

```
sudo ./kp release --release-version 23  --release-arch x86_64 --release-title "My Korora" \
--release-codename "custom" --desktop GNOME korora-gnome
```

<a name="boot-your-image"></a>
## Boot your image!

Now you can try to boot that with KVM or a real machine!
