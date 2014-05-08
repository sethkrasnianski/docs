<!--
@title Create new entry in a flow
@author Moltin Ltd
@description Inserts a new entry into the flow
@order 15.3.3

@sidebar 1
@family Flow/Entry
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This endpoint allows you to insert an entry into the flow.

#### Resource URL
POST [{{ url }}flow/:slug/entry]({{ url }}flow/:slug/entry)


#### Paramaters
Available fields vary based on the fields in this flow

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "105",
        "title": "Hello everyone",
        "description": "This is a successful entry insertion"
    }
}

```


#### Example Invalid Slug Response
``` json
{
    "status": false,
    "errors": [
        "Title is required"
    ]
}
```
<!--/code-->