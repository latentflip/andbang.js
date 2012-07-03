#And Bang API Client
### Makes it dead simple to build web apps on the And Bang API. 

- All API functionality becomes a function call.
- Couldn't be any simpler

Just inclide the script in your HTML
```html
<script src="andbang.js"></script>
```

Then write some JS

```js
// init an instance of the API connection
var api = new AndBang();

// then log in
api.validateToken('your access token', function (err, yourUser) {
    window.me = yourUser;
});

// 'ready' is triggered when you're successfully logged in
api.on('ready', function () {
    // once 'ready' has been triggered 
    // all your normal API functions are available
    // as function calls.

    // for example, we can just fetch our teams
    // and pass it a callback.
    api.getTeams(function (err, myTeams) {
        window.teams = myTeams;
    });
});
```

It uses socket.io under the covers so you get realtime, seemless API access that's as easy as AJAX.

Have fun!