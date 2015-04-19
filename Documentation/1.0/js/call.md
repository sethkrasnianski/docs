# Making a call

- [Introduction](#introduction)
- [Asynchronous](#async)
- [Synchronous](#sync)
- [Event](#event)

<a name="introduction"></a>
## Introduction

After [authenticating](authentication) you will now have a token that will allow you to access certain resources for a store. The access that they grant you varies on the type of authentication method used.

With this example you'll be shown how to get a product from the API and view its data so you know what you're dealing with.

<a name="async"></a>
## Asynchronous

``` js
var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
moltin.Authenticate(function() {

	// Your code here...

});
```

<a name="sync"></a>
## Synchronous

``` js
var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
moltin.Authenticate();

// Your code here...
```

<a name="event"></a>
## Event

``` js
var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
moltin.Authenticate();

window.addEventListener('MoltinReady', function(response) {
	// Your code here...
});
```
