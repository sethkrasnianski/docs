<!--
@title Update single tax band
@author Moltin Ltd
@description Updates a tax band with the given ID
@order 11.1

@sidebar 1
@family Tax
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a tax band with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}tax/:id]({{ url }}tax/:id)


#### parameters
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The title of this tax band
description*optional* | String | A short description of this tax band
rate*optional* | Decimal | The default tax rate (can be changed on a per-currency basis)

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": 8,
    "title": "My awesome tax band",
    "description": "No... Awesome products are exempt from taxes!",
    "rate": "0.00",
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
        "rate": "0.00"
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
        "rate": "0.00"
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
        "rate": "0.00"
      }
    ]
  }
}
```


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "The rate must be a number."
  ]
}
```
<!--/code-->