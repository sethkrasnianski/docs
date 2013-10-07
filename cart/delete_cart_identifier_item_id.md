<!--
@title DELETE cart/:identifier/item/:id
@author Moltin Ltd
@description Removes an item from the cart

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->


Deleting an item from a users cart is as simple as calling the item URL with a DELETE HTTP method.


#### Resource URL	{#resource}
DELETE [{{ url }}cart/:identifier/item/:id]({{ url }}cart/:identifier/item/:id])


#### Paramaters	{#paramaters}
None required


#### Example Successful Response	{#success}
``` json
{
    "status": true
}
```

#### Example Failed Response	{#error}
``` json
{
    "status": false
}
```
