This call deletes an address with a given ID. Once an address has been deleted all orders with that address will become unknown.

#### Resource URL
DELETE [{{ api_url }}addresses/:id/address/:id]({{ api_url }}addresses/:id/address/:id)


#### Parameters
N/A

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Address deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": true,
    "message": "Address not found"
}
```
<!--/code-->