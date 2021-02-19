---
title: /wgytcraft.cf/build_modules
parent: /wgytcraft.cf
---
# [documentation.wgyt.tk](https://documentation.wgyt.tk)/[wgytcraft.cf](https://documentation.wgyt.tk/wgytcraft.cf)/build_modules
___
## Example error page:
You need to create a github repo and add a file:

```javascript
// index.js
module.exports = function(host,res,req,errornumber,errordesc,version,ejs){
	res.status(errornumber);
	res.send(ejs.render(`<!DOCTYPE html>
<html lang="en" class="text-white bg-blue-900 antialiased">

<head>
code here
</head>
<body>
code here
</body>
`, {}));
}

```
Change the HTML to your liking and then your done!
## Example hello world site
You need to create a github repo or fork wgytcraft/hello-world-template and add a file:
```javascript
module.exports = function(host, res, req, error, version, ejs){
  res.send('hello world!')
}
```
Change the HTML to your liking and then your done!
