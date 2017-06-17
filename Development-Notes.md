These are notes on the development of this section and will be removed when the wiki is operational. **Anyone with suggestions feel free to add or comment.**

This project started as a result of the discussion on https://github.com/kororaproject/website/issues/55 and also the request from a number of people to allow contributions by pull requests.

## Recent Changes
Footer - added, copied from the website  
Sidebar - added, however not really required unless it is intended that the wiki be used as the documentation site. Needs manual addition of new pages.

## Suggestions
~~It was suggested that we create a separate repo for documentation, - "if you really want to be able to use PRs for documentation you can use a normal github repo to do the PRs on and the repo owners (those with push permissions) can manually sync to the wiki repo when new documentation is added/accepted"
If this is done it may be better to move this wiki to that repo.  
This would also solve the image storage issue as covered in https://github.com/kororaproject/website/issues/56~~ Done  
After some trial and error it was found that for images to appear on kp.org they need to use the full path with ?raw=true appended.  
It may be necessary to create a Contribution Guidelines doc to simplify acceptance of contributions. One possible issue is image names which could be duplicated. Suggest names reflect the document they attach to.
## Categorise Docs
add folders to categorise 
### Installation Etc. 
covers getting, installing, upgrading and updating
### Using and Tip
cover using, Tip and Tricks, could get very large, 
### Support and Development
covers getting help and developing

## Sync to Site
2 documents have been added that cover the most common needs to sync to the website.  
First is a totally new document (albeit with formatting that is not supported on the site) - https://github.com/kororaproject/website/wiki/Working-With-Archives  
Second is an existing document that has been edited - https://github.com/kororaproject/website/wiki/Which-Desktop-for-Your-Korora  
An alternative to syncing back to the website would be to use the wiki and change the link on the website. This change would require the approval of the core team.
### Known Incompatibilites
The Korora website accepts HTML in documentation but it is ignored on Github.  
The Korora site doesn't handle tables which work on Github