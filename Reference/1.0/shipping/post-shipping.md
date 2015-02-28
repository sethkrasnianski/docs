<!--
@title Create new shipping method
@author Moltin Ltd
@description Creates a new shipping method

@sidebar 1
@family Shipping
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This endpoint creates a new shipping method with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new shipping method will be returned.


#### Resource URL
POST [{{ api_url }}shipping]({{ api_url }}shipping)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title | String | The shipping method's title
slug | String | The shipping method's slug
company | String | The shipping method's company
status | Integer | The shipping method's status (1 or 0)
price | Decimal | The shipping method's price
price_min*optional* | Decimal | The shipping method's minimum price
price_max*optional* | Decimal | The shipping method's maximum price
weight_min*optional* | Decimal | The shipping method's minumum weight
weight_max*optional* | Decimal | The shipping method's maximum weight
description*optional* | String | The shipping method's description
tax_band | Integer | The shipping method's tax band id

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": "154",
    "title": "Free Shipping",
    "slug": "free",
    "company": "FedEx",
    "status": {
      "key": "1",
      "value": "Live"
    },
    "price": "0",
    "price_min": "10.00",
    "price_max": "100.00",
    "weight_min": "10.00",
    "weight_max": "100.00",
    "description": "Free shipping on orders between £10 and £100",
    "tax_band": {
      "id": 1,
      "title": "Default",
      "description": null,
      "rate": "20.00"
    }
  }
}
```


#### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "Invalid choice specified for Status"
  ]
}
```
<!--/code-->