<!--
@title GET flows/type/:slug
@author Moltin Ltd
@description Get a single field type
@order 15.17

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a single field type with its available options.

#### Resource URL
GET [{{ url }}flows/type/:slug]({{ url }}flows/type/:slug)


#### Paramaters
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