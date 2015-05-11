This call deletes a product with a given ID or a set of products in a comma-seperated list of IDs.

#### Resource URL
DELETE [{{ api_url }}products/:id[,:id]]({{ api_url }}products/:id[,:id])


#### Parameters
None required


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