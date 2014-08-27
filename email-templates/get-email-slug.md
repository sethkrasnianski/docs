<!--
@title Get email template by slug
@author Moltin Ltd
@description Returns an email template of the given slug

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns an email template based on a given slug.


#### Resource URL
[{{ url }}email/:slug]({{ url }}email/:slug)


#### Parameters
None required

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


### Example Empty Response
``` json
{
  "status": false,
  "error": "Currency not found"
}
```
<!--/code-->