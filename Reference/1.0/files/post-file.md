<!--
@title Create new file
@author Moltin Ltd
@description Creates a new file

@sidebar 1
@family Files
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

This endpoint creates a new file with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new file will be returned.


#### Resource URL
POST [{{ api_url }}file]({{ api_url }}file)


#### Parameters
Key | Type | Description
--- | ---- | -----------
file | File | The file to upload
name | String | The name of the file
assign_to | Integer | The resource ID that this image relates to

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 672,
        "url": {
            "http": "http://commercecdn.com/1/db072334-3f20-4801-8e22-2a4d205e4f67.jpeg",
            "https": "https://commercecdn.com/1/db072334-3f20-4801-8e22-2a4d205e4f67.jpeg"
        },
        "segments": {
            "domain": "commercecdn.com/",
            "suffix": "/1/db072334-3f20-4801-8e22-2a4d205e4f67.jpeg"
        }
    }
}
```


#### Example Failed Response
``` json
{
    "status": false,
    "errors": [
        "The file field is required."
    ]
}
```
<!--/code-->