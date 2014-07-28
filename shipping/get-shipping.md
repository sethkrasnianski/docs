<!--
@title Get shipping methods by criteria
@author Moltin Ltd
@description Gets a list of shipping methods based on the given criteria

@sidebar 1
@family Shipping
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a paginated list of shipping methods based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}shipping]({{ url }}shipping)


#### parameters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
title*optional* | String | Select by title
slug*optional* | String | Select by slug
company*optional* | String | Select by company
status*optional* | Integer | Select by status (1 or 0)
price*optional* | Decimal | Select by price
price_min*optional* | Decimal | Select by minimum price
price_max*optional* | Decimal | Select by maximum price
weight_min*optional* | Decimal | Select by minumum weight
weight_max*optional* | Decimal | Select by maximum weight
description*optional* | String | Select by description
tax_band*optional* | Integer | Select by tax band id

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
    {
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
  ],
  "pagination": {
    "total": 1,
    "current": 1,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 1,
    "offsets": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    },
    "links": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    }
  }
}
```


### Example Empty Response
``` json
{
  "status": true,
  "result": [],
  "pagination": {
    "total": 0,
    "current": 0,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 0,
    "offsets": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    },
    "links": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    }
  }
}
```
<!--/code-->