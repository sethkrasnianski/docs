<!--
@title Delete order by ID
@author Moltin Ltd
@description Deletes an order with a given ID

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes an order with a given ID.

#### Resource URL
DELETE [{{ api_url }}orders/:id]({{ api_url }}orders/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Order deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
  "status": false,
  "message": "No order found"
}
```
<!--/code-->
