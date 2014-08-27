<!--
@title Delete cart and contents
@author Moltin Ltd
@description Destroys a cart and its' item contents
@order 4.7

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This method is used to destroy an entire shopping cart, this can not be undone.


#### Resource URL
DELETE [{{ url }}cart/:identifier]({{ url }}cart/:identifier])


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "message": "Cart destroyed"
}
```
<!--/code-->