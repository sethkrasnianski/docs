<!--
@title Create order item
@author Moltin Ltd
@description Creates a new item for a specified order

@sidebar 1
@family Order/Order Item
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This endpoint allows you to update item quantaties in an order.


#### Resource URL
POST [{{ api_url }}order/:id/item]({{ api_url }}order/:id/item)


#### Parameters
Key | Type | Description
--- | ---- | -----------
product*optional* | Integer | Link this item to a product
sku*required* | String | The item SKU
title*required* | String | The item title
price*required* | Float | The item price
quantity*required* | Integer | The quantity of this item
tax_rate*required* | Float | The current tax rate for this item
tax_band*required* | Integer | The tax band for this item

<!--code-->
#### Example Successful Response
``` json
{
   "status": true,
   "result":
   {
       "id": "1007",
       "product": null,
       "sku": "test123",
       "title": "Test 1 2 3",
       "price": "19.99",
       "quantity": 1,
       "tax_rate": "0.00",
       "tax_band":
       {
           "value": "Default",
           "data":
           {
               "id": 1,
               "title": "Default",
               "description": null,
               "rate": "20.00",
               "created_at": null,
               "updated_at": null
           }
       },
       "created_at": "2014-06-10 10:29:40",
       "updated_at": "2014-06-10 10:29:40"
   }
}
```


### Example Failed Response
``` json
{
    "status": false,
    "errors":
    [
        "SKU is required",
        "Product Title is required",
        "Price is required",
        "Quantity is required",
        "Tax Rate is required",
        "Tax Band is required"
    ]
}
```
<!--/code-->