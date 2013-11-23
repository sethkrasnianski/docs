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
DELETE [{{ url }}product/:id[,:id]]({{ url }}product/:id[,:id])


#### Paramaters
None required

#### PHP (SDK) Example
``` php
	$result = $moltin->delete('product/15');

	if ( ! $result['status'] ) {
		throw new Exception($result['error']);
	}
```

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Product deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
	"status": false,
	"error": "Product does not exist"
}
```
<!--/code-->