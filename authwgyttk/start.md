---
title: /auth.wgyt.tk/start
parent: /auth.wgyt.tk
---
# [documentation.wgyt.tk](https://documentation.wgyt.tk)/[authwgyttk](https://documentation.wgyt.tk/authwgyttk)/start
_________________
_How to get started with Wgyt Auth_
## Test it and make sure it works
Go to `https://auth.wgyt.tk/?url=[yoursite]` replacing [yoursite] with your website's url.  
Login and look at the URL.  
![Image of Chrome Tab](https://u.cubeupload.com/wgyt/Screenshot20210111at.png)  
We can see a few parts:  
`https://[yoursite]/auth/callback/` is the URL that Wgyt Auth redirects to  
`?id=3956341` is the user's ID  
`&name=WilliamHorning` is the user's username  
`&roles=teacher,student,self_learner,explorer` is the user's roles.  
We can use these query strings to get data about the user.

### To use it on your site see [documentation.wgyt.tk](https://documentation.wgyt.tk)/[authwgyttk](https://documentation.wgyt.tk/authwgyttk)/[code](https://documentation.wgyt.tk/authwgyttk/code/)
