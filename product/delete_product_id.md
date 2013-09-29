<!--
@title DELETE product/:id
@author Moltin Ltd
@description Deletes a product with a given ID or in a comma-seperated list of IDs

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a product with a given ID or a set of products in a comma-seperated list of IDs.

#### Resource URL
DELETE [{{ url }}product/:id]({{ url }}product/:id)

DELETE [{{ url }}product/:id,:id,...]({{ url }}product/:id,:id,...)


#### Paramaters
N/A

#### Example Successful Response
``` json
{
    "status": true,
    "message": "Product deleted successfully"
}
```

#### Example Invalid ID Response
``` json
TBA
```
