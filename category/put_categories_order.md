<!--
@title PUT categories/order
@author Moltin Ltd
@description Orders and sets the parents of a set of given cateories

@sidebar 1
@family Categories
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->

You can update the order and parents of categories in one go. This is useful if you have some sort of drag-n-drop system in place to reorder your categories.

#### Paramaters	{#paramaters}
Key | Type | Parent | Description
--- | ---- | ------ | -----------
:id[parent] | Integer | <id> | The parent category
:id[order] | Integer | <id> | The order in which this category appears


<!--code-->
#### Example Successful Response	{#success}
``` json
{
  "status": true
}
```


### Example Failed Response	{#error}
``` json
{
  "status": false,
  "errors": {}
}
```
<!--/code-->