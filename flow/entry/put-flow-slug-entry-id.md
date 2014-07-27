<!--
@title Update an entry in a flow
@author Moltin Ltd
@description Updates an entry in the specified flow
@order 15.3.4

@sidebar 1
@family Flow/Entry
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint allows you to update an entry from the specified flow.

#### Resource URL
PUT [{{ url }}flow/:slug/entry/:id]({{ url }}flow/:slug/entry/:id)


#### parameters
Available fields vary based on the fields in this flow

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "105",
        "title": "Hello again",
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