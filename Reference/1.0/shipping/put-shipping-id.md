<!--
@title Update a shipping method
@author Moltin Ltd
@description Updates a shipping method with the given ID

@sidebar 1
@family Shipping
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint edits a shipping method with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ api_url }}shipping/:id]({{ api_url }}shipping/:id)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The shipping method's title
slug*optional* | String | The shipping method's slug
company*optional* | String | The shipping method's company
status*optional* | Integer | The shipping method's status (1 or 0)
price*optional* | Decimal | The shipping method's price
price_min*optional* | Decimal | The shipping method's minimum price
price_max*optional* | Decimal | The shipping method's maximum price
weight_min*optional* | Decimal | The shipping method's minumum weight
weight_max*optional* | Decimal | The shipping method's maximum weight
description*optional* | String | The shipping method's description
tax_band*optional* | Integer | The shipping method's tax band id

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
    "price_max": "1000.00",
    "weight_min": "10.00",
    "weight_max": "100.00",
    "description": "Free shipping on orders between £10 and £1000",
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