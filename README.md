Assurity Canvas
=======
This is a modified version of Canvas LMS for use as the back-end of Assurity Education Community.

### Changes
- Login does not use Oauth - adapted to simply accept a username and password
- Extra fields for User's position, city, and company
- Forgotten password page redirects to front-end React site

### Setup
- Either follow the Quickstart (tested) or production start (untested) instructions below onto a cloud server (we currently are hosting one on AWS t3 medium)
- See [here](https://github.com/instructure/canvas-lms/wiki/Canvas-Integration) for instructions to set up AWS for file storage, currently uses one of Team primer's AWS s3 buckets
- Configure outgoing email [here](https://github.com/instructure/canvas-lms/wiki/Production-Start#outgoing-mail-configuration) - currently sends emails only for forgotten passwords - no activation or confirmation emails sent
- Edit `config/domain.yml` file (this gets created in the Quickstart instructions) to contain the correct ip address
- `public/javascripts/ajax_errors.js` file is hard-coded to redirect to our current live front-end. This should be changed to the address of the Assurity hosted Canvas Front-end
- If using Quickstart, you'll also need to start the [delayed job](https://github.com/WesleyYep/Pre-Post-Course-System/wiki/How-to-run-background-worker-on-Canvas-backend-server) and don't forget about [data setup](https://github.com/instructure/canvas-lms/wiki/Quick-Start#data-setup)
- Copy the address of the Canvas site into the [constants.js](https://github.com/WesleyYep/Pre-Post-Course-System/blob/master/pre-post-course-system/imports/lib/constants.js) file on the react application. If not using SSL, just copy the same address to both address fields (and port)
- Go to the address of the Canvas site in a browser. You should see the Canvas default login page. Login with the admin account details that it would have prompted to create during the install. Hover cursor over "Courses" and choose the default account that you created (not site admin).
- Go to "Settings" on the left side menu. Ensure "SIS Import", "Enable Profiles", "Users can edit name" and "User avatars" are checked.

### Recommended
- Set username and password of postgres database (the connection strings in `imports/api/actions` files of the front-end application may need to change to take the username and password into account)
- Set SSL (both for canvas and meteor back-end)

Canvas LMS
======

Canvas is a new, open-source LMS by Instructure Inc. It is released under the
AGPLv3 license for use by anyone interested in learning more about or using
learning management systems.

[Please see our main wiki page for more information](http://github.com/instructure/canvas-lms/wiki)

Installation
=======

Detailed instructions for installation and configuration of Canvas are provided
on our wiki.

 * [Quick Start](http://github.com/instructure/canvas-lms/wiki/Quick-Start)
 * [Production Start](http://github.com/instructure/canvas-lms/wiki/Production-Start)
