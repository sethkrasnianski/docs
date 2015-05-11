This call creates a new tax band with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new tax band will be returned.


#### Resource URL
POST [{{ api_url }}taxes]({{ api_url }}taxes)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title | String | The title of this tax band
description*optional* | String | A short description of this tax band
rate | Decimal | The default tax rate (can be changed on a per-currency basis)

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": 8,
    "title": "My awesome tax band",
    "description": "Awesome products are charged tax at 99% right?...",
    "rate": "99.00",
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
        "rate": "99.00"
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
        "rate": "99.00"
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
        "rate": "99.00"
      }
    ]
  }
}
```


#### Example Empty Response
``` json
{
  "status": false,
  "errors": [
    "The title field is required.",
    "The rate field is required."
  ]
}
```
<!--/code-->