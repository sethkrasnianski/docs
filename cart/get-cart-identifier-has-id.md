<!--
@title GET cart/:identifier/has/:id
@author Moltin Ltd
@description Checks if the cart contains an item of a given identifier
@order 4.5

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Checks if the cart contains the specified item identifier


#### Resource URL
GET [{{ url }}cart/:identifier/has/:id]({{ url }}cart/:identifier/has/:id])


#### Paramaters
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