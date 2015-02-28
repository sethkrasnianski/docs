This call deletes a customer's address with a given IDs. Once a customer has been deleted all orders with that address will become anonymous.

#### Resource URL
DELETE [{{ api_url }}customer/:id/address/:id]({{ api_url }}customer/:id/address/:id)


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