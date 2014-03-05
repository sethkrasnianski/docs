<!--
@title GET flow/:slug
@author Moltin Ltd
@description Get a single flow based on the specified slug 

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a single flow with the specified slug.

#### Resource URL
GET [{{ url }}flow/:slug]({{ url }}flow/:slug)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "name": "My awesome custom flow",
        "slug": "my-awesome-custom-flow",
        "info": "Flows are awesome!",
        "title_column": "awesome_field"
    }
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->