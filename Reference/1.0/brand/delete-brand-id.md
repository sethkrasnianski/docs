This call deletes a brand with a given ID. Once a brand has been deleted all products will lose that brand.

#### Resource URL
DELETE [{{ api_url }}brands/:id]({{ api_url }}brands/:id)


#### Parameters
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
