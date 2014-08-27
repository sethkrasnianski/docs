<!--
@title Get all field types
@author Moltin Ltd
@description Get a list of the available field types
@order 15.1.1

@sidebar 1
@family Flow/Field Type
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a list of the available field types and their options.

#### Resource URL
GET [{{ url }}flows/types]({{ url }}flows/types)


#### Parameters
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