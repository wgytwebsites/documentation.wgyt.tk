---
title: /wgytcraft.cf/modules.json_docs
parent: /wgytcraft.cf
---
# [documentation.wgyt.tk](https://documentation.wgyt.tk)/[wgytcraft.cf](https://documentation.wgyt.tk/wgytcraft.cf)/build_modules
___
## Version:
Type: _string_  
This is just a version variable that can match the version in index.js but can also be used to version the modules.json file.
Example:
```json
"version":"0.1-alpha",
```
## Module List:
Type: _array_  
This is the array containing the github repo slug.  
Example: 
```json 
"moduleList":[ 
	"wgytcraft/errors",
	"wgytcraft/hello-world-template"
],
```
## Error Handler:
Type: _string_  
This is the github repo slug for the error handler. It must be imported in the Module List.
Example:
```json
"errorHandler":"wgytcraft/errors",
```
## website
Type: _array_  
This is the array containing an array of sites that are allowed to be served.
Example:
```json
"website":["test.wgyt.tk"],
```
## Website Modules
Type: _object_  
This is the object containing an object of sites and which module should serve it.
Example:
```json
"websiteModules":{
	"test.wgyt.tk":"wgytcraft/hello-world-template"
}
```
