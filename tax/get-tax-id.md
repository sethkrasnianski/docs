<!--
@title Get tax band by ID
@author Moltin Ltd
@description Returns a tax band of the given ID
@order 11.7

@sidebar 1
@family Tax
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a tax band based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}tax/:id]({{ url }}tax/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": 3,
    "store_id": 1,
    "title": "Tax Band 2",
    "description": "Test",
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
  "status": false,
  "error": "Tax not found"
}
```
<!--/code-->