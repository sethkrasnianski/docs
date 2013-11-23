<!--
@title PUT gateway/:slug
@author Moltin Ltd
@description Updates a gateway with the given slug

@sidebar 1
@family Gateway
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->

This method edits a gateway with a given slug.


#### Resource URL	{#resource}
PUT [{{ url }}gateway/:slug]({{ url }}gateway/:slug)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
name*optional* | String | The name of the gateway
description*optional* | String | The description of this gateway
settings[] | Array | An array of gateway settings specific to the gateway you are updating

<!--code-->
#### Example Successful Response	{#success}
``` json
{
  "status": true,
  "result": {
    "settings": {
      "username": "moltinpp",
      "password": "password",
      "signature": "swirly-with-a-trailing-flick",
      "testMode": true,
      "solutionType": "Sole",
      "landingPage": "Billing",
      "headerImageUrl": "http://docs.dev.molt.in/assets/img/logo.png"
    },
    "slug": "paypal-express",
    "name": "PayPal Express"
  }
}
```


### Example Failed Response	{#error}
``` json
{
  "status": false,
  "errors": [
    "The Username setting is required",
    "The Password setting is required",
    "The Signature setting is required",
    "The Test Mode setting is required",
    "The Solution Type setting is required",
    "The Landing Page setting is required",
    "The selected Landing Page setting is invalid"
  ]
}
```
<!--/code-->