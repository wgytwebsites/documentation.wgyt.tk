---
title: /wgytcraft.cf
---
# [documentation.wgyt.tk](https://documentation.wgyt.tk)/wgytcraft.cf
_________________
## Error Codes:
Most Errors Codes Are Just HTTP status codes with an extra description.
### This Site Doesn't exist error:
This site is not set up for use with wgytcraft.cf
## Modules:
### How to build:
#### Example error page:
You need to create a github repo and add a few files:

```javascript
// index.js
module.exports = function(host,res,req,errornumber,errordesc,version,ejs){
	ejs.renderFile('modules/filename/index.ejs', {errornumber: errornumber,errordesc:errordesc,url:`https://${host}${req.url}`,host:host||wgytcraft,timestamp:0,version:version}, {}, function (err, template) { if (err) { throw err; } else { res.end(template); } }); 
}
```
```ejs 
<!-- index.ejs -->
your website here
```
Change the files to your liking and then your done!
### List:
#### wgytcraft/errors
Description: _beautiful tailwind error pages, powered by ejs, inspired by wgyt.tk, shipped with wgytcraft, by default_

Github Repo: https://github.com/wgytcraft/errors
