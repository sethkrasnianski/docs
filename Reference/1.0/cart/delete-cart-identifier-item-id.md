Deleting an item from a users cart is as simple as calling the item URL with a DELETE HTTP method.


#### Resource URL
DELETE [{{ api_url }}carts/:identifier/items/:id]({{ api_url }}carts/:identifier/items/:id])


#### Parameters
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