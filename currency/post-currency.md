<!--
@title Create new currency
@author Moltin Ltd
@description Creates a new currency

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new currency with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new currency will be returned.


#### Resource URL
POST [{{ url }}cateogry]({{ url }}cateogry)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
code | String | The currency code (i.e. GBP)
title | String | The currency title
enabled | Boolean | Enabled or Disabled? 1 or 0 
modifier*optional* | String | The currency modifier (i.e. +1) 
exchange_rate*optional* | Float | The exchange rate
format*optional* | String | The currency format (i.e. £{price})
decimal_point*optional* | String | The decimal point symbol
thousand_point*optional* | String | The thousand separator symbol
rounding*optional* | Enumeration (50, 99, full) | The currency rounding (i.e. 50, 99, full)
default*optional* | Bollean | Is this the default currency? 1 or 0

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": 17,
    "store_id": 1,
    "code": "USD",
    "title": "US Dollar",
    "enabled": true,
    "modifier": "+0",
    "exchange_rate": null,
    "format": "${price}",
    "decimal_point": ".",
    "thousand_point": ",",
    "rounding": null,
    "default": false
  }
}
```


### Example Empty Response
``` json
{
  "status": false,
  "errors": [
    "The code has already been taken."
  ]
}
```
<!--/code-->