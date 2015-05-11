<!--
@title Delete file by ID
@author Moltin Ltd
@description Deletes a file with the specified ID

@sidebar 1
@family Files
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This call deletes a file with a given ID. Once a file has been deleted all items will lose that file.

#### Resource URL
DELETE [{{ api_url }}files/:id]({{ api_url }}files/:id)


#### Parameters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "File removed successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "File not found"
}
```
<!--/code-->