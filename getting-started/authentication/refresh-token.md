<!--
@title Refresh Token
@author Moltin Ltd
@description Before you start making calls you need to Authenticate
@family Getting Started/Authentication
@order 1.1.3
@sidebar 1
-->

The refresh_token grant type is used to refresh an access token which you retrieved from the authorization_code grant type to prevent you needing to reauthenticate the user every time the access token expires.

#### Authorizing with Refresh Token
Authorizing with a refresh token is very similar to using client credentials, except you need to pass over your refresh token as well. You will not be sent another refresh token back, you can keep using the same refresh token every time your access token expires.

#### Resource URL
POST [https://api.molt.in/oauth/access_token](https://api.molt.in/oauth/access_token)

#### Paramaters
Key | Type | Description | Value
--- | ---- | ----------- | -----
grant_type | String | The grant type to use | refresh_token
client_id | String | Your client id
client_secret | String | Your client secret
refresh_token | String | The refresh token

<!--code-->
#### Example Successful Response
``` json
{
    "access_token": "bXbJUbPGxfDBFerVtMuGYl8AxKNYhdRt0eCblyfl",
    "token_type": "bearer",
    "expires": 1405000406,
    "expires_in": 3600
}
```
<!--/code-->