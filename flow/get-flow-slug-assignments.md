<!--
@title GET flow/:slug/assignments
@author Moltin Ltd
@description Deletes a flow with a given slug
@order 15.6

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This endpoint displays all the assignments for a specified slug.

#### Resource URL
GET [{{ url }}flow/:slug/assignments]({{ url }}flow/:slug/assignments)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "title": {
            "slug": "title",
            "name": "Title",
            "type": "string",
            "options": [],
            "required": false,
            "unique": false,
            "locked": false,
            "order": null,
            "value": null
        },
        "description": {
            "slug": "description",
            "name": "Description",
            "type": "text",
            "options": [],
            "required": false,
            "unique": false,
            "locked": false,
            "order": null,
            "value": null
        }
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