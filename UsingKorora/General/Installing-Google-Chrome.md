

**Table of Contents**  

- [Installing Google Chrome](#installing-google-chrome)
    - [Testing Versions](#testing-versions)



<a name="installing-google-chrome"></a>
# Installing Google Chrome

Korora includes FireFox as its default browser but many people prefer Google Chrome. Unfortunately Chrome cannot be distributed in Korora due to its licensing restrictions. However it is simple to install Chrome in any version of Korora.

Korora comes with many repos already set up so you can just install many software packages from the Package Manager or command line. One of the repos that is set up is Google Chrome.

To install Google Chrome use the command `sudo dnf install google-chrome`. This will install the stable version of Google Chrome.

<a name="testing-versions"></a>
## Testing Versions
As well as the stable version, Google makes available versions of Chrome for testing. These are the beta and unstable versions. These versions can be installed in Korora but first you need to edit the repo file.

> Do not install these versions unless you are comfortable handling the issues that sometimes arise using test software.

Using your preferred text editor open `/etc/yum.repos.d/google-chrome.repo`, you will need to prefix the command with `sudo`. The last line is an exclude statement. You will need to delete or comment out this line. Alternatively you could edit it by removing the version you wish to install from that line.

The beta version will install with the command `sudo dnf install google-chrome-beta`.

The unstable version will install with the command `sudo dnf install google-chrome-unstable`.
