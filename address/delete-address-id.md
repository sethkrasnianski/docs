<!--
@title Delete address by ID
@author Moltin Ltd
@description Deletes an address with the specified ID

@sidebar 1
@family Address
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This call deletes a customer's address with a given IDs. Once a customer has been deleted all orders with that address will become anonymous.

#### Resource URL
DELETE [{{ url }}customer/:id/address/:id]({{ url }}customer/:id/address/:id)


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