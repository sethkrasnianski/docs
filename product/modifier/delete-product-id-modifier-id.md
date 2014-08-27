<!--
@title Delete product modifier by ID
@author Moltin Ltd
@description Deletes a product modifier with a given ID
@order 3.1.6

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a product modifier with a given ID or a set of modifiers in a comma-seperated list of IDs.

#### Resource URL
DELETE [{{ url }}product/:productId/modifier/:id[,:id]]({{ url }}product/:productId/modifier/:id[,:id])

#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Product Modifier deleted successfully"
}
```

#### Example Invalid ID Response
``` json
{
	"status": false,
	"error": "Product Modifier does not exist"
}
```

#### PHP (SDK) Example
``` php
$result = $moltin->delete('product/15/modifier/100');

if ( ! $result['status'] ) {
	throw new Exception($result['error']);
}
```
<!--/code-->