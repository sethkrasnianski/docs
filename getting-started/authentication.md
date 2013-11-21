<!--
@title Authentication
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@family Getting Started
-->
Before using the API you must first authenticate with it, this will allow it to retrieve the correct data for your account as well as keep your data safe and secure. For anyone already familiar with OAuth from other places this should be a very easy process, for those not so you'll find all the help you need below.

## OAuth 2.0
OAuth is an open standard for authorization. OAuth provides a method for clients to access server resources on behalf of a resource owner (such as a different client or an end-user). It also provides a process for end-users to authorize third-party access to their server resources without sharing their credentials (typically, a username and password pair), using user-agent redirections.

The Moltin API uses [OAuth 2.0](http://oauth.net/2/) to authenticate requests and we have several grant types integrated.

### Grant Types
With OAuth 2.0 there are a number of different grant types available which require different types of credentials and are designed for different purposes.

The different grant types that are available are as follows:

##### Client Credentials
The easiest grant type to get started with. Designed to grant access to your own store using your own client id and secret. This grant type is designed to be used on your storefront and does not require you to redirect or login.

##### Authorization Code
Designed for apps which may integrate with numerous stores (i.e. accountancy app or price comparison website). This grant type is for developers of third party apps and requires the store owner to login to authorize the application before access is granted. This is the most common OAuth 2.0 grant type and will be familiar to those of you who have ever used Facebook to login to an app or website.

#### Authorising with Client Credentials
To authorize with client credentials you simply need to post your client id and client secret to the https://api.molt.in/oauth/access_token. If all goes well then you will receive a response with your access
token.

``` json
{
  "access_token": "7LKQe9urWbIGYf7WCjqiainYgy9KrL1aayJl2sQq",
  "token_type": "Bearer",
  "expires": 1385050869,
  "expires_in": 3600
}
```

#### Authorizing with Authorization Code
Authorizing with the authorization code grant type is a little more complicated than client credentials. Below is a diagram of how the authorization code grant type works.

```
+--------+                               +---------------+
|        |--(A)- authorisation Request ->|   Resource    |
|        |                               |     Owner     |
|        |<-(B)-- authorisation Grant ---|               |
|        |                               +---------------+
|        |
|        |                               +---------------+
|        |--(C)-- authorisation Grant -->| authorisation |
| Client |                               |     Server    |
|        |<-(D)----- Access Token -------|               |
|        |                               +---------------+
|        |
|        |                               +---------------+
|        |--(E)----- Access Token ------>|    Resource   |
|        |                               |     Server    |
|        |<-(F)--- Protected Resource ---|               |
+--------+                               +---------------+
```

### Client Libraries
#### PHP
#### Objective-C
#### Java
#### Python
#### Ruby
#### .NET
#### C++
