

**Table of Contents**  

- [ISO Testing](#iso-testing)



# ISO Testing

Before being released all Korora ISO's should be checked that they provide the best possible experience and don't include any problems that reflect poorly on our project. A set testing routine aims to achieve a consistent standard across all Korora systems.

This is based on the testing procedure used for Korora 21 ISO's. It has been added to from that experience. This should be considered the minimum requirement. Feel free to add and improve.

1. After downloading the iso's verify that the checksum matches, either with md5-, sha1- or sha256sum.

2. Once the iso's are burned to DVD or copied to a usb-stick with dd and you boot from the install media, make sure to run 'Test this media & start Korora....' first to see if it passes the test.

3. Check if they boot (preferably on both msdos and UEFI)

4. Do a sudo dnf distro-sync and make sure all our packages are in, and not some updated fedora ones that slipped in, which now want to update to Korora packages.

5. After the desktop loaded, check if 'Korora Welcome' is displayed.

6. Test to see if all the apps work.

7. Test to see if the default apps are right, e.g. touch movie.mkv and see if it opens in VLC, etc.. Check text files open in editor and not LibreOffice.

8. Test Firefox to make sure it works with the addons that are included by default.

9. Test and look if all the addons are there and working.

10. Obviously make sure the theme and stuff is right.

11. Install the OS, preferably on a real machine as well as VM.

12. Make sure languages work . Test installing in different languages.

13. Make sure users are created and that in post install everything works as expected.
