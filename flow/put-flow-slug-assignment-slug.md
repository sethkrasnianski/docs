<!--
@title PUT flow/:slug/assignment/:assignmentSlug
@author Moltin Ltd
@description Get a single assignment from a flow
@order 15.8

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
You can update assignments for any field, including the default Moltin assignments. However, you are restricted to updating only the assignment title on the default assignments.

#### Resource URL
PUT [{{ url }}flow/:slug/assignment/:assignmentSlug]({{ url }}flow/:slug/assignment/:assignmentSlug)

#### Paramaters
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