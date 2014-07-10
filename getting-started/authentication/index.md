<!--
@title Client Credentials
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@order 1.1.0
@sidebar 1
-->

Before using the API you must first authenticate with it, this will allow it to retrieve the correct data for your account as well as keep your data safe and secure. For anyone already familiar with OAuth from other places this should be a very easy process, for those not so you'll find all the help you need below.

## OAuth 2.0
OAuth is an open standard for authorization. OAuth provides a method for clients to access server resources on behalf of a resource owner (such as a different client or an end-user). It also provides a process for end-users to authorize third-party access to their server resources without sharing their credentials (typically, a username and password pair), using user-agent redirections.

The Moltin API uses [OAuth 2.0](http://oauth.net/2/) to authenticate requests and we have several grant types integrated.

When you create a store on our website, you will be given a client id and secret. You can use these tokens to authenticate and gain access to the API.

### Client Libraries
#### [PHP](https://github.com/moltin/php-sdk)
#### [Javascript](https://github.com/moltin/js-sdk)
#### [C#](https://github.com/moltin/csharp-sdk)