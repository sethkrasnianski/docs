<!--
@title DELETE flow/:slug
@author Moltin Ltd
@description Deletes a flow with a given slug

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This endpoint deletes a flow with the specified slug. Only flows you created can be deleted, flows created by Moltin are locked.

#### Resource URL
DELETE [{{ url }}flow/:id]({{ url }}flow/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Flow deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->