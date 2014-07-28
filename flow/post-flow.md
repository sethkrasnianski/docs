<!--
@title Create new flow
@author Moltin Ltd
@description Creates a new flow
@order 15.7

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This endpoint allows you to create a new flow.


#### Resource URL
POST [{{ url }}flow]({{ url }}flow)


#### parameters
Key | Type | Description
--- | ---- | -----------
name | String | The name of the flow
slug | String | The slug of the flow (must be unique)
info*optional* | String | A short description about the flow

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "name": "My awesome custom flow",
        "slug": "my-awesome-custom-flow",
        "info": "Flows are awesome!",
        "title_column": null
    }
}
```


### Example Failed Response
``` json
{
    "status": false,
    "errors": [
        "The name field is required.",
        "The slug field is required."
    ]
}
```
<!--/code-->