<!--
@title Get single currency by criteria
@author Moltin Ltd
@description Gets a currency based on the given criteria

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a currency based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}currency]({{ url }}currency)


#### parameters
Key | Type | Description
--- | ---- | -----------
code*optional* | String | The currency code (i.e. GBP)
title*optional* | String | The currency title
enabled*optional* | Boolean | Enabled or Disabled? 1 or 0 
modifier*optional* | String | The currency modifier (i.e. +1) 
exchange_rate*optional* | Float | The exchange rate
format*optional* | String | The currency format (i.e. £{price})
decimal_point*optional* | String | The decimal point symbol
thousand_point*optional* | String | The thousand separator symbol
rounding*optional* | Enumeration (50, 99, full) | The currency rounding (i.e. 50, 99, full)
default*optional* | Boolean | Is this the default currency? 1 or 0

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
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
  }
}
```


### Example Failed Response
``` json
{
    "status": false,
    "error": "No currency found"
}
```
<!--/code-->