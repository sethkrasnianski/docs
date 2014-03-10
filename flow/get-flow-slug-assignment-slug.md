<!--
@title GET flow/:slug/assignment/:assignmentSlug
@author Moltin Ltd
@description Get a single assignment from a flow
@order 15.7

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a single assignment from the specified flow and with the specified assignment slug.

#### Resource URL
GET [{{ url }}flow/:slug/assignment/:assignmentSlug]({{ url }}flow/:slug/assignment/:assignmentSlug)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "slug": "title",
        "name": "Title",
        "type": "string",
        "options": [],
        "required": false,
        "unique": false,
        "locked": false,
        "order": null
    }
}
```

#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->