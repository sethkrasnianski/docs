<!--
@title DELETE cart/:identifier
@author Moltin Ltd
@description Destroys a cart and its' item contents

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->

This method is used to destroy an entire shopping cart.


#### Resource URL	{#resource}
DELETE [{{ url }}cart/:identifier]({{ url }}cart/:identifier])


#### Paramaters	{#paramaters}
None required


#### Example Successful Response	{#success}
``` json
{
    "status": true,
    "message": "Cart destroyed"
}
```
