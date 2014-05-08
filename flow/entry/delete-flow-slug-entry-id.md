<!--
@title Delete flow entry by ID
@author Moltin Ltd
@description Deletes the specified entry from the flow
@order 15.3.5

@sidebar 1
@family Flow/Entry
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This endpoint allows you delete an entry from the flow you specify.

#### Resource URL
DELETE [{{ url }}flow/:slug/entry/:id]({{ url }}flow/:slug/entry/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Entry deleted successfully"
}

```


#### Example Invalid Slug Response
``` json
{
    "status": false,
    "errors": [
        "Entry not found"
    ]
}
```
<!--/code-->