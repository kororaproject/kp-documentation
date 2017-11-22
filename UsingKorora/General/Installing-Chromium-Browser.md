Installing Chromium Browser

While Firefox has always been the default browser in Korora many people like to add another browser. One of the most popular ones is [Google's Chrome](https://kororaproject.org/support/documentation/installing-google-chrome) browser. However Chrome also has an opensource sibling, **Chromium**, which is now in the repos. That means it is easy to add to Korora.

Chromium looks and works the same as Chrome however it is often a version or 2 behind. It is a popular option for those who want something different to Firefox  but still want to use open source.

### Installation
As Chromium is in the repos it is simple to install. A simple `sudo dnf install chromium` will install the browser and the required libs packages. 

However the standard chromium-libs-media package does not include all the available codecs etc. required for many websites. Fortunately an extended version, **chromium-lib-media-freeworld** is available from RPMFusion. This includes the extra libs needed as well as those included in the standard package. It is fine to have both packages installed together however only the freeworld version is needed.

As the RPMFusion repo is already active in Korora, Chromium can be installed complete with the extended Meda libs with  `sudo dnf install chromium chromium-libs-media-freeworld`. Alternatively you can search for both packages in your preferred Package Manager.