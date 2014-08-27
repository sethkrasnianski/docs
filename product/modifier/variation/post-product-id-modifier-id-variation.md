<!--
@title Create new product variation
@author Moltin Ltd
@description Creates a new product variation
@order 3.1.1.5

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new product variation with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new variation will be returned.

#### Resource URL
POST [{{ url }}product/:productId/modifier/:modifierId/variation]({{ url }}product/:productId/modifier/:modifierId/variation)

#### Parameters
Key | Type | Description
--- | ---- | -----------
title | String | The Title of the variation, must be unique per modifier
mod_price*optional* | String | Pricing modifier, a decimal prefixed with +, - or = (eg. +0.50, -1.50, =5.99)

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "524",
        "title": "Red",
        "mod_price": " 0.50",
        "modifier": 523,
        "product": 0,
        "created_at": "2014-05-07 10:57:58",
        "updated_at": "2014-05-07 10:57:58"
    }
}
```

#### Example Invalid Title Response
``` json
{
    "status": false,
    "errors":
    [
        "The title must be unique for the modifier"
    ]
}
```
<!--/code-->