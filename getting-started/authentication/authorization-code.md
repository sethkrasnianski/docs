<!--
@title Authorization Code
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@family Getting Started/Authentication
@order 1.1.2
@sidebar 1
-->

Designed for apps which may integrate with numerous stores (i.e. accountancy app or price comparison website). This grant type is for developers of third party apps and requires the store owner to login to authorize the application before access is granted. This is the most common OAuth 2.0 grant type and will be familiar to those of you who have ever used Facebook to login to an app or website.

#### Authorizing with Authorization Code
Authorizing with the authorization code grant type is a little more complicated than client credentials. On the right there is a diagram of how the authorization code grant type works.

### Step 1
First you need to redirect to Moltin with some information so your user can login to grant access

#### URL
GET [https://auth.molt.in/oauth](https://auth.molt.in/oauth)

#### Paramaters
Key | Type | Description | Value
--- | ---- | ----------- | -----
client_id | String | Your client id
redirect_uri | String | The URL to redirect back to when the user has authorized your app
state | String | A unique and random string that you can use to match against when the user comes back
scope | String | A comma separated list of scopes you need access to for your app to function
response_type | String | The type of response you'd like to receive | code


### Step 2
After the user has authorized your app, the user will be redirected back to the redirect_uri that you provided with some data that you can use to complete the request. You will then need to exchange your code for an access token which will grant you access to the API.

#### Resource URL
POST [https://api.molt.in/oauth/access_token](https://api.molt.in/oauth/access_token)

#### Paramaters
Key | Type | Description | Value
--- | ---- | ----------- | -----
grant_type | String | The grant type to use | authorization_code
client_id | String | Your client id
client_secret | String | Your client secret
code | String | The code which was passed back to your application
redirect_uri | String | The URL you used when authorizing

<!--code-->
#### The Authorization code flow
``` json
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

#### Example Successful Response
``` json
{
    "access_token": "7LKQe9urWbIGYf7WCjqteljYgy9KrL1aayJl2sQq",
    "token_type": "Bearer",
    "expires": 1404999022,
    "expires_in": 3600,
    "refresh_token": "JpllFt6o9qSYKA7WCMOx0MurIH75haMcgjgR4xhG"
}
```
<!--/code-->