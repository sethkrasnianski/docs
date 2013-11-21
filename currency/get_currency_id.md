<!--
@title GET currency/:id
@author Moltin Ltd
@description Returns a currency of the given ID

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a currency based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL	{#resource}
[{{ url }}currency/:id]({{ url }}currency/:id)


#### Paramaters	{#paramaters}
None required


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


### Example Empty Response	{#error}
``` json
{
  "status": false,
  "error": "Currency not found"
}
```
