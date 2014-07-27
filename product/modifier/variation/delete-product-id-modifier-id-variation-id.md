<!--
@title Delete product variation by ID
@author Moltin Ltd
@description Deletes a product variation with a given ID
@order 3.1.1.6

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a product variation with a given ID or a set of modifiers in a comma-seperated list of IDs.

#### Resource URL
DELETE [{{ url }}product/:productId/modifier/:modifierId/variation:id[,:id]]({{ url }}product/:productId/modifier/:modifierId/variation:id[,:id])

#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Product Variation deleted successfully"
}
```

#### Example Invalid ID Response
``` json
{
	"status": false,
	"error": "Product Variation does not exist"
}
```

#### PHP (SDK) Example
``` php
$result = $moltin->delete('product/15/modifier/100/variation/105');

if ( ! $result['status'] ) {
	throw new Exception($result['error']);
}
```
<!--/code-->