<!--
@title GET tax
@author Moltin Ltd
@description Gets a tax band based on the given criteria

@sidebar 1
@family Tax
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a tax band based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}tax]({{ url }}tax)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
title*optional* | String | Select by tax band title
description*optional* | String | Select by tax band description
rate*optional* | Decimal | The tax rate (percentage)

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": 1,
    "store_id": 1,
    "title": "Default",
    "description": null,
    "rate": "20.00",
    "currencies": [
      {
        "id": 7,
        "code": "GBP",
        "title": "British Pound",
        "enabled": true,
        "modifier": "*3",
        "exchange_rate": "1.00",
        "format": "£{price}",
        "decimal_point": ".",
        "thousand_point": ",",
        "rounding": "full",
        "default": false,
        "rate": "20.00"
      },
      {
        "id": 9,
        "code": "EUR",
        "title": "Euro",
        "enabled": false,
        "modifier": "*0",
        "exchange_rate": "1.20",
        "format": "€{price}",
        "decimal_point": ",",
        "thousand_point": ",",
        "rounding": null,
        "default": false,
        "rate": "20.00"
      },
      {
        "id": 17,
        "code": "USD",
        "title": "US Dollar",
        "enabled": true,
        "modifier": "+0",
        "exchange_rate": null,
        "format": "${price}",
        "decimal_point": ".",
        "thousand_point": ",",
        "rounding": null,
        "default": false,
        "rate": "20.00"
      }
    ]
  }
}
```


### Example Empty Response
``` json
{
  "status": true,
  "result": []
}
```
<!--/code-->