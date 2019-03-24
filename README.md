# Twice-Media-API
Public API/client library like thing to get Twice Media

## TODO
### Create Script for Organizing Files Locally Before Upload
  - [ ] Reorganize the directories based on the following file structure
    - [ ] Certain keywords are automatically found (fansign, concert) that will programmatically rename the folder's name to `[Date]_[type]_[Original name]`
    - [ ] If those keywords are not found, the folder's path will be added to a text file to later rename by hand.
    - [X] Extract any `_Press` folders into the main event folder.
    - [X] Move any `_group` folder images to the group folder if the group folder doesn't already contain that image.
    - [X] Delete any other subfolders that reside inside of them (like low quality pictures)
  - [ ] Rename all the files inside of the folders based on the folder names (this is applies locally only, the online file structure will be different) 
    - E.g. if a file is in `./tzuyu/yes-or-yes/123456_concert`, the first image gets named `123456_1.jpg`, the second image gets named `123456_1.jpg`, and so on.
### Create Script for uploading files
   - [ ] Create a script to upload it to google drive, with the following requirements
   - [ ] Takes in the path of where the file was `./tzuyu/yes-or-yes/123456_concert/123456_4.png`, then based on that path, it will add tags.
   - [ ] Adds metadata based on the filename e.g. `123456_concert_1.jpg` gets the tag of `date='123456'`, `type='concert'`, `member='membernamehere'`
### Create script/api for interacting with already uploaded files
  - [ ] Create a script (that's connected to a webserver this time), that can act like an API to query the files in the drive using the tags. 
    - [ ] Script should ideally have the ability to choose a random picture if a tag is not specified e.g. `era` or `type`
    - [ ] Consider using serverless code instead (AWS lambda, google cloud functions) since there probably won't be enough queries to warrant a full on API server
