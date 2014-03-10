<!--
@title GET flow/:slug/entry/:id
@author Moltin Ltd
@description Returns a single entry based on the specified ID
@order 15.12

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This endpoint will return a single entry for the ID you specified.

#### Resource URL
GET [{{ url }}flow/:slug/entry/:id]({{ url }}flow/:slug/entry/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "102",
        "title": "Hello universe",
        "description": "Hello universe, how are you today?"
    }
}

```


#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Entry not found"
}
```
<!--/code-->