<!--
@title DELETE collection/:id
@author Moltin Ltd
@description Deletes a collection with the specified ID

@sidebar 1
@family Collection
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This call deletes a collection with a given ID. Once a collection has been deleted all products will lose that collection.

#### Resource URL
DELETE [{{ url }}collection/:id]({{ url }}collection/:id)


#### Paramaters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Collection deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": true,
    "message": "Collection not found"
}
```
<!--/code-->