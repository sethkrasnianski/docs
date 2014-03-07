<!--
@title DELETE flow/:slug/assignment/:assignmentSlug
@author Moltin Ltd
@description Delete an assignment from a flow
@order 15.10

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
With this endpoint you can delete an assignment from a flow. You can delete any assignment from a flow you created, but you are limited to deleting only your own assignments from default Moltin flows.

#### Resource URL
DELETE [{{ url }}flow/:slug/assignment/:assignmentSlug]({{ url }}flow/:slug/assignment/:assignmentSlug)

#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Assignment unassigned successfully"
}
```

#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Assignment not found"
}
```
<!--/code-->