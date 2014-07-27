<!--
@title Get single field type by slug
@author Moltin Ltd
@description Get a single field type
@order 15.2.2

@sidebar 1
@family Flow/Field Type
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a single field type with its available options.

#### Resource URL
GET [{{ url }}flows/type/:slug]({{ url }}flows/type/:slug)


#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
TBA
```

#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->