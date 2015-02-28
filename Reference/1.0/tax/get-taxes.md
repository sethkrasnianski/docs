Returns a range of tax bands based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ api_url }}taxes]({{ api_url }}taxes)


#### Parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of tax bands to return, defaults to all
offset*optional* | Integer | The first tax band to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
    {
      "id": 1,
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
    },
    {
      "id": 3,
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
  ]
}
```


#### Example Empty Response
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