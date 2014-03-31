<!--
@title Update category order & set parents
@author Moltin Ltd
@description Orders and sets the parents of a set of given cateories
@order 2.6

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->

You can update the order and parents of categories in one go. This is useful if you have some sort of drag-n-drop system in place to reorder your categories.

#### Resource URL   {#resource}
PUT [{{ url }}categories/order]({{ url }}categories/order)

#### Paramaters
Key | Type | Description
--- | ---- | -----------
:id[parent] | Integer | The parent category
:id[order] | Integer | The order in which this category appears


<!--code-->
#### Example Successful Response
``` json
{
  "status": true
}
```


### Example Failed Response
``` json
{
  "status": false,
  "errors": []
}
```
<!--/code-->