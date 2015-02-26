<!--
@title Update a currency
@author Moltin Ltd
@description Updates a currency with the given ID

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a currency with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL {#resource}
PUT [{{ url }}currency/:id]({{ url }}currency/:id)


#### Parameters {#parameters}
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
#### Example Successful Response  {#success}
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


### Example Empty Response  {#error}
``` json
{
  "status": false,
  "errors": [
    "The code has already been taken."
  ]
}
```
<!--/code-->
