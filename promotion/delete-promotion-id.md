<!--
@title Delete promotion by ID
@author Moltin Ltd
@description Deletes a promotion with a given ID
@order 2.7

@sidebar 1
@family Promotion
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a promotion with a given ID or a set of categories in a comma-seperated list of IDs. Once a promotion has been deleted all products in that promotion will be removed and possibly unavailable. 

#### Resource URL
DELETE [{{ url }}promotion/:id[,:id]]({{ url }}promotion/:id[,:id])


#### Parameters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Promotion deleted successfully"
}
```


#### Example Invalid ID Response
``` json
TBA
```
<!--/code-->