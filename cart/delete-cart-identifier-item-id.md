<!--
@title Delete item from cart
@author Moltin Ltd
@description Removes an item from the cart
@order 4.6

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->


Deleting an item from a users cart is as simple as calling the item URL with a DELETE HTTP method.


#### Resource URL
DELETE [{{ url }}cart/:identifier/item/:id]({{ url }}cart/:identifier/item/:id])


#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true
}
```

#### Example Failed Response
``` json
{
    "status": false
}
```
<!--/code-->