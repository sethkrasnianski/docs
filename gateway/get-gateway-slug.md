<!--
@title Get gateway by slug
@author Moltin Ltd
@description Returns a gateway of the given slug

@sidebar 1
@family Gateway
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a gateway based on a given slug. The gateway settings will also be returned as an array.


#### Resource URL
[{{ url }}gateway/:slug]({{ url }}gateway/:slug)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "name": "Stripe",
    "slug": "stripe",
    "description": "Because, what other gateway would I ever need?",
    "enabled": false,
    "settings": {
      "apiKey": "my-secret-key"
    }
  }
}
```


### Example Empty Response
``` json
{
  "status": false,
  "error": "Gateway not found"
}
```
<!--/code-->