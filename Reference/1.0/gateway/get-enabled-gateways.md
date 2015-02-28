<!--
@title Get enabled gateways
@author Moltin Ltd
@description Gets an array of enabled gateways

@sidebar 1
@family Gateway
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns all enabled gateways


#### Resource URL
GET [{{ api_url }}gateways/enabled]({{ api_url }}gateways/enabled)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
   {
      "name": "Stripe",
      "slug": "stripe",
      "description": "This is my desc",
      "enabled": true,
      "settings": {
         "apiKey": "hello"
      }
   },
   {
      "name": "Manual",
      "slug": "manual",
      "description": null,
      "enabled": true,
      "settings": [
      
      ]
   }
  ]
}
```
<!--/code-->