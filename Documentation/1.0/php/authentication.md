# Authentication

- [Introduction](#introduction)
- [Client Credentials](#client-credentials)
- [Password](#password)
- [Refresh](#refresh)

<a name="introduction"></a>
## Introduction

Moltin leverages the industry standard OAuth2 system giving you safe and secure use of the API in any scenario. Each of these different methods are called a grant type and are designed to fit around different use cases.

After authenticating with the API using one of these methods you will recieve an access token which will allow you access to a specific store and in some cases a limited number of endpoints. These tokens are only valid for an hour and after this time it will no longer work. Some grant types are returned with a refresh token to be used with the refresh grant type, allowing you to gain a new access token without a user having to reinput their credentials.

> **Note:** Your credientials are listed in the account section on the Moltin website, after you click 'view keys' for a store.

<a name="client-credentials"></a>
## Client Credentials

This is the most basic grant type available and is designed for secure, server-side applications where the source code is hidden. The client credientials method requires both the client id and secret and as such is not intended to be used by any application which may be distributed or used on client machines.

``` php
Moltin::Authenticate('ClientCredentials', array(
	'client_id'     => '<YOUR CLIENT ID>',
	'client_secret' => '<YOUR CLIENT SECRET>'
));
```

<a name="password"></a>
## Password

The password method is intended for third-party applications wanting access to anothers stores data, and is the method used on [forge](forge) to give users access to their data. This method allows you to use your keys, as well as an email and password combination from a third-party to retrieve an access token for that store. 

``` php
Moltin::Authenticate('Password', array(
	'username'      => '<USERS EMAIL>',
	'password'      => '<USERS PASSWORD>',
	'client_id'     => '<YOUR CLIENT ID>',
	'client_secret' => '<YOUR CLIENT SECRET>'
));
```

> **Note:** After an hour these tokens are invalid but have a refresh token to use without the user having to login again.

<a name="refresh"></a>
## Refresh

The refresh method is not strictly an authentication method as it relies on already having used one and is simply intended to continue use certain grant types without the users input again. This token is invalid indefinatley and can be revoked by the user at any time via the accounts section of the Moltin website.

``` php
Moltin::Authenticate('Refresh', array(
	'refresh_token' => '<REFRESH TOKEN>',
	'client_id'     => '<YOUR CLIENT ID>',
	'client_secret' => '<YOUR CLIENT SECRET>'
));
```

> **Note:** After refreshing you will not get another refresh token and should continue to use the current one.