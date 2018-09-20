# xlui.app

Here is the source code of https://xlui.app, I upload this to github for
continous deployment using [Jenkins](https://jenkins.io/). Setting a github 
push webhook and configuring jenkins for third-part remote build, when I 
push a update of the site, github will send a post request to the configured 
url and this will trigger jenkins's build process which is configured for
copying the content of folder `website` to the webroot of https://xlui.app.

It is very convenient. Now, when I want to update the content of https://xlui.app,
I just need to push the updates to github, and that's all!
