<!--
@title Get single field for a flow by slug
@author Moltin Ltd
@description Get a single field from a flow
@order 15.2.2

@sidebar 1
@family Flow/Field
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a single field from the specified flow and with the specified field slug.

#### Resource URL
GET [{{ api_url }}flows/:slug/fields/:fieldSlug]({{ api_url }}flows/:slug/fields/:fieldSlug)


#### Parameters
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