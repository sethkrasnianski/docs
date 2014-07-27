<!--
@title Get multiple currencies by criteria
@author Moltin Ltd
@description Gets an array of currencies

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a list of currencies that have been setup. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ url }}currencies]({{ url }}currencies)


#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
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
      "default": false
    },
    {
      "id": 8,
      "code": "USD",
      "title": "US Dollar",
      "enabled": false,
      "modifier": "+1",
      "exchange_rate": "2.00",
      "format": "${price}",
      "decimal_point": ".",
      "thousand_point": ",",
      "rounding": "full",
      "default": false
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
      "default": false
    }
  ]
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