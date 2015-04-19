# Authentication

- [Introduction](#introduction)
- [Always Authenticate](#always)
- [Implicit](#implicit)

<a name="introduction"></a>
## Introduction

Moltin leverages the industry standard OAuth2 system giving you safe and secure use of the API in any scenario. Each of these different methods are called a grant type and are designed to fit around different use cases.

After authenticating with the API using one of these methods you will recieve an access token which will allow you access to a specific store and in some cases a limited number of endpoints. These tokens are only valid for an hour and after this time it will no longer work. Some grant types are returned with a refresh token to be used with the refresh grant type, allowing you to gain a new access token without a user having to reinput their credentials.

> **Note:** Your credientials are listed in the account section on the Moltin website, after you click 'view keys' for a store.

<a name="always"></a>
## Always Authenticate

You should include this authentication call either surrounding you code (Asyncronous/Event) or before (Synchronous) you attempt to make any calls in your application. The SDK caches the access token and does not attempt to reauthenticate before it has expired.

<a name="implicit"></a>
## Implicit

This is the only grant type available to the JavaScript SDK and is intended as a 'read-only' authentication. Designed for distributed applications this method grants access to the API by only providing a client_id (not secret).

> **Note:** Because of the authentication type only access to specific end points are granted for essential reads, a limited number of writes and some disabled resources (such as orders, customers).

#### Asynchronous

	var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
	moltin.Authenticate(function() {
		// Your code here...
	});

#### Synchronous

	var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
	moltin.Authenticate();

	// Your code here...

#### Event

	var moltin = new Moltin({publicId: '<YOUR PUBLIC ID>'});
	moltin.Authenticate();

	window.addEventListener('MoltinReady', function(response) {
		// Your code here...
	});