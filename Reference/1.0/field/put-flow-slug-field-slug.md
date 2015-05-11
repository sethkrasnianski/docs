<!--
@title Update a field in a flow by slug
@author Moltin Ltd
@description Update a field that already exists
@order 15.2.4

@sidebar 1
@family Flow/Field
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
You can update fields for any field, including the default Moltin fields. However, you are restricted to updating only the field title on the default fields.

#### Resource URL
PUT [{{ api_url }}flows/:slug/fields/:fieldSlug]({{ api_url }}flows/:slug/fields/:fieldSlug)

#### Parameters
Key | Type | Description
--- | ---- | -----------
name*optional* | String | The name of the field
slug*optional* | String | The field slug
type*optional* | String | The type of field
options*optional* | Array | The options for this field type
required*optional* | Choice (1 or 0) | Is this field required?
unique*optional* | Choice (1 or 0) | Should this field be unique?

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "slug": "title",
        "name": "My updated title",
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