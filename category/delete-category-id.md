<!--
@title DELETE category/:id
@author Moltin Ltd
@description Deletes a category with a given ID or in a comma-seperated list of IDs
@order 2.7

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a category with a given ID or a set of categories in a comma-seperated list of IDs. Once a category has been deleted all products in that category will be removed and possibly unavailable. 

#### Resource URL
DELETE [{{ url }}category/:id[,:id]]({{ url }}category/:id[,:id])


#### Paramaters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Category deleted successfully"
}
```


#### Example Invalid ID Response
``` json
TBA
```
<!--/code-->