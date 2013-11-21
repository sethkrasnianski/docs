<!--
@title GET cart/:identifier/has/:id
@author Moltin Ltd
@description Checks if the cart contains an item of a given identifier

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Checks if the cart contains the specified item identifier


#### Resource URL	{#resource}
GET [{{ url }}cart/:identifier/has/:id]({{ url }}cart/:identifier/has/:id])


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
