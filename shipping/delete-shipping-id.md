<!--
@title Delete shipping method by ID
@author Moltin Ltd
@description Deletes a shipping method with a given ID

@sidebar 1
@family Shipping
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This method deletes a shipping method with a given ID. Once a shipping method has been deleted all orders for that shipping method will become anonymous.

#### Resource URL
DELETE [{{ url }}shipping/:id]({{ url }}shipping/:id)


#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Shipping method deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "message": "Shipping method not found"
}
```
<!--/code-->