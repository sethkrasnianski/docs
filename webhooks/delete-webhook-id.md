<!--
@title Delete webhook by id
@author Moltin Ltd
@description Deletes an webhook with a given id

@sidebar 1
@family Webhooks
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a webhook with the specified id.

#### Resource URL
DELETE [{{ url }}webhook/:id]({{ url }}webhook/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Webhook removed successfully"
}
```


#### Example Invalid ID Response
``` json
{
  "status": false,
  "error": "Webhook not found"
}
```
<!--/code-->