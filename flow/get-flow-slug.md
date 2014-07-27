<!--
@title Get flow by slug
@author Moltin Ltd
@description Get a single flow based on the specified slug
@order 15.6

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


#### parameters
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

#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->