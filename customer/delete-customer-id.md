<!--
@title DELETE customer/:id
@author Moltin Ltd
@description Deletes a customer with a given ID

@sidebar 1
@family Customer
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This method deletes a customer with a given ID. Once a customer has been deleted all orders and addresses for that customer will become anonymous. Addresses which have not been used in an order will be permanently deleted.

#### Resource URL	{#resource}
DELETE [{{ url }}customer/:id]({{ url }}customer/:id)


#### Paramaters	{#paramaters}
None required

<!--code-->
#### Example Successful Response	{#success}
``` json
{
    "status": true,
    "message": "Customer deleted successfully"
}
```


#### Example Invalid ID Response	{#error}
``` json
{
    "status": false,
    "message": "Customer not found"
}
```
<!--/code-->