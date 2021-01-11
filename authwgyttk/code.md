# [documentation.wgyt.tk](https://documentation.wgyt.tk)/[authwgyttk](https://documentation.wgyt.tk/authwgyttk)/code
_________________
_How to code projects with Wgyt Auth support_
## If you use Express JS
Add this to the top of your main file:  
```
const mustacheExpress = require('mustache-express');
const cookieParser = require('cookie-parser');
app.use(cookieParser());
app.engine('html', mustacheExpress());
app.set('views', './views');
app.set('view engine', 'html');
app.use(express.json());
app.use('/data', express.static(`${__dirname}/data`));
```
You will also need to add this below that code you added
```
// Auth
app.get('/auth', (req, res) => {
	res.sendFile(`${__dirname}/views/auth.html`)
})
app.get('/auth/callback', (req, res) => {
	res.render('authcall', {
		userid: req.query.id,
		username: req.query.name,
		userroles: req.query.roles
	})
})
```
You will also need to create a file in the views folder called `auth.html` that contains:
```
<meta http-equiv="refresh" content="0;url=https://auth.wgyt.tk/?url=[yoursite]" />
```
replacing [yoursite] with your website's URL.  
You will also need to create a file in the views folder called `authcall.html` that contains:
```
<script>
document.cookie = "id={{userid}}; expires=Thu, 18 Dec 2030 12:00:00 UTC; path=/";
document.cookie = "name={{username}}; expires=Thu, 18 Dec 2030 12:00:00 UTC; path=/";
document.cookie = "roles={{userroles}}; expires=Thu, 18 Dec 2030 12:00:00 UTC; path=/";
if (true){
	setTimeout(() => {  window.close(); }, 5000);
}
</script>
```
This sets the cookies `id` `name` and `roles` to the values in the query strings.  
You should also add more code in `authcall.html` that does something like redirecting the user to the page that they were logging in to.  
## If you don't use Express JS
You should deal with the query strings and set cookies based on the content.  

| Query String | Cookie Name |
| ----------- | ----------- |
| id | id |
| name | name |
| roles | roles |

## How to check for login (using html)  
### If you need to allow only one user:
Add the following code to your head tag:
```
	<script>
		if ('{{userid}}'===''){
				window.location.assign('https://auth.wgyt.tk/?url=wgyt.cf/dash')
			}
		if ('{{userid}}'!=='[thatuserid]'){
				window.location.assign('https://auth.wgyt.tk/?url=wgyt.cf/dash')
			}
	</script>
 ```
 Replacing [thatuserid] for that user's ID.
 ### If you need to allow any user:
 Add the following code to your head tag:
```
	<script>
		if ('{{userid}}'===''){
				window.location.assign('https://auth.wgyt.tk/?url=wgyt.cf/dash')
			}
	</script>
 ```
## That's it!
