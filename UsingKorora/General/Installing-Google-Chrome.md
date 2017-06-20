<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Installing Google Chrome](#installing-google-chrome)
  - [Testing Versions](#testing-versions)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Installing Google Chrome

Korora includes FireFox as its default browser but many people prefer Google Chrome. Unfortunately Chrome cannot be distributed in Korora due to its licensing restrictions. However it is simple to install Chrome in any version of Korora.

Korora comes with many repos already set up so you can just install many software packages from the Package Manager or command line. One of the repos that is set up is Google Chrome.

To install Google Chrome use the command `sudo dnf install google-chrome`. This will install the stable version of Google Chrome.

## Testing Versions
As well as the stable version, Google makes available versions of Chrome for testing. These are the beta and unstable versions. These versions can be installed in Korora but first you need to edit the repo file.

> Do not install these versions unless you are comfortable handling the issues that sometimes arise using test software.

Using your preferred text editor open `/etc/yum.repos.d/google-chrome.repo`, you will need to prefix the command with `sudo`. The last line is an exclude statement. You will need to delete or comment out this line. Alternatively you could edit it by removing the version you wish to install from that line.

The beta version will install with the command `sudo dnf install google-chrome-beta`.

The unstable version will install with the command `sudo dnf install google-chrome-unstable`.
