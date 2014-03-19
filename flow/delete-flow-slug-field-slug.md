<!--
@title DELETE flow/:slug/field/:fieldSlug
@author Moltin Ltd
@description Delete a field from a flow
@order 15.10

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
With this endpoint you can delete a field from a flow. You can delete any field from a flow you created, but you are limited to deleting only your own fields from default Moltin flows.

#### Resource URL
DELETE [{{ url }}flow/:slug/field/:fieldSlug]({{ url }}flow/:slug/field/:fieldSlug)

#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Field unassigned successfully"
}
```

#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Field not found"
}
```
<!--/code-->