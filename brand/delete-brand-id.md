<!--
@title Delete brand by ID
@author Moltin Ltd
@description Deletes a brand with the specified ID

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This call deletes a brand with a given ID. Once a brand has been deleted all products will lose that brand.

#### Resource URL
DELETE [{{ url }}brand/:id]({{ url }}brand/:id)


#### parameters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Brand deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": true,
    "message": "Brand not found"
}
```
<!--/code-->