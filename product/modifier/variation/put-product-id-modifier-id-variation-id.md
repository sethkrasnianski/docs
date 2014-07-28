<!--
@title Update a product variation
@author Moltin Ltd
@description Updates a product variation with the given ID
@order 3.1.1.6

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a product variation with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.

#### Resource URL
PUT [{{ url }}product/:productId/modifier/:modifierId/variation/:id]({{ url }}product/:productId/modifier/:modifierId/variation/:id)

#### parameters
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
        "mod_price": "-0.50",
        "modifier": 523,
        "product": 0,
        "created_at": "2014-05-07 10:57:58",
        "updated_at": "2014-05-07 11:03:26"
    }
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "errors": [
    	"Title must be unique"
    ]
}
```
<!--/code-->