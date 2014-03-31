<!--
@title Get all fields for a flow
@author Moltin Ltd
@description Returns all the fields for a given flow
@order 17.1

@sidebar 1
@family Flow Field
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This endpoint displays all the fields for a specified slug.

#### Resource URL
GET [{{ url }}flow/:slug/fields]({{ url }}flow/:slug/fields)


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