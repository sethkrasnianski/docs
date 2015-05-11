<!--
@title Enable gateway
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
Enables a gateway based on a given slug.


#### Resource URL
GET [{{ api_url }}gateways/:slug/enable]({{ api_url }}gateways/:slug/enable)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Gateway enabled successfully"
}
```


#### Example Empty Response
``` json
{
  "status": false,
  "error": "Gateway not found"
}
```
<!--/code-->