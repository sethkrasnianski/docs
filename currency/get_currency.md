<!--
@title GET category
@author Moltin Ltd
@description Gets a category based on the given criteria

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a currency based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL	{#resource}
[{{ url }}currency]({{ url }}currency)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
code*optional* | Integer | The currency code (i.e. GBP)
title*optional* | Integer | The currency title
enabled*optional* | Integer | Enabled or Disabled? 1 or 0 
modifier*optional* | Integer | The currency modifier (i.e. +1) 
exchange_rate*optional* | Integer | The exchange rate
format*optional* | Integer | The currency format (i.e. £{price})
decimal_point*optional* | Integer | The decimal point symbol
thousand_point*optional* | Integer | The thousand separator symbol
rounding*optional* | Integer | The currency rounding (i.e. 50, 99, full)
default*optional* | Integer | Is this the default currency? 1 or 0


#### Example Successful Response	{#success}
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


### Example Failed Response	{#error}
``` json
{
    "status": false,
    "error": "No currency found"
}
```
