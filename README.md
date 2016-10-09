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
- `public/javascripts/ajax_errors.js` file is hard-coded to redirect to our current live front-end. This should be changed to the address of the Assurity hosted Canvas Front-end
- If using Quickstart, you'll also need to start the [delayed job](https://github.com/WesleyYep/Pre-Post-Course-System/wiki/How-to-run-background-worker-on-Canvas-backend-server)
- Copy the address of the live site into the [constants.js](https://github.com/WesleyYep/Pre-Post-Course-System/blob/master/pre-post-course-system/imports/lib/constants.js) file on the react application. If not using SSL, just copy the same address to both address fields (and port)

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
