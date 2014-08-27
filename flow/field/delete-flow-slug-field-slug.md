<!--
@title Delete flow field by slug
@author Moltin Ltd
@description Delete a field from a flow
@order 15.2.5

@sidebar 1
@family Flow/Field
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
With this endpoint you can delete a field from a flow. You can delete any field from a flow you created, but you are limited to deleting only your own fields from default Moltin flows.

#### Resource URL
DELETE [{{ url }}flow/:slug/field/:fieldSlug]({{ url }}flow/:slug/field/:fieldSlug)

#### Parameters
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