<!--
@title Client Credentials
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@family Getting Started/Authentication
@order 1.1.1
@sidebar 1
-->

The easiest grant type to get started with. Designed to grant access to your own store using your own client id and secret. This grant type is designed to be used on your storefront and does not require you to redirect or login.

#### Authorising with Client Credentials
To authorize with client credentials you simply need to post your client id and client secret to the https://api.molt.in/oauth/access_token. If all goes well then you will receive a response with your access token.

#### Resource URL
POST [https://api.molt.in/oauth/access_token](https://api.molt.in/oauth/access_token)

#### Paramaters
Key | Type | Description | Value
--- | ---- | ----------- | -----
grant_type | String | The grant type to use | client_credentials
client_id | String | Your client id
client_secret | String | Your client secret

<!--code-->
#### Example Successful Response
``` json
{
  "access_token": "7LKQe9urWbIGYf7WCjqteljYgy9KrL1aayJl2sQq",
  "token_type": "Bearer",
  "expires": 1385050869,
  "expires_in": 3600
}
```
<!--/code-->