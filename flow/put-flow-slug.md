<!--
@title Update a flow
@author Moltin Ltd
@description Updates a flow
@order 15.8

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint allows you to update one of your flows. You can only update custom flows, flows created by Moltin are locked.


#### Resource URL
PUT [{{ url }}flow/:slug]({{ url }}flow/:slug)


#### Parameters
Key | Type | Description
--- | ---- | -----------
name*optional* | String | The name of the flow
slug*optional* | String | The slug of the flow (must be unique)
info*optional* | String | A short description about the flow

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "name": "My awesome updated custom flow",
        "slug": "my-awesome-custom-flow",
        "info": "Flows are even more awesome when they can be updated!",
        "title_column": null
    }
}
```


### Example Failed Response
``` json
{
    "status": false,
    "errors": [
        "Slug must be unique"
    ]
}
```
<!--/code-->