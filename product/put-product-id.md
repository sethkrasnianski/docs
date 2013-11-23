<!--
@title PUT product/:id
@author Moltin Ltd
@description Updates a product with the given ID

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a product with a given ID. There are no minumum required paramaters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.

#### Resource URL
PUT [{{ url }}product/:id]({{ url }}product/:id)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
sku*optional* | String | The SKU of the product, must be unique
title*optional* | String | The Title of the product, must be unique
slug*optional* | String | The Slug/URI of the product, must be unique
price*optional* | Float | The Price of the product
status*optional* | Choice (1 or 0) | Is the product Live or a Draft
category*optional* | Integer | The Category of the product
stock_level*optional* | Integer | The Stock Level of the product
stock_status*optional* | Choice (0 to 6) | The Stock Status of the product
description*optional* | String | The Description of the product
requires_shipping*optional* | Choice (1 or 0) | Does the product require Shipping?
sale_price*optional* | Float | The Sale Price of the product
weight*optional* | Float | The Weight of the product, used in shipping calculations
height*optional* | Float | The Height of the product, used in shipping calculations
width*optional* | Float | The Width of the product, used in shipping calculations
depth*optional* | Float | The Depth of the product, used in shipping calculations

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 26,
        "title": "Test Product 10 (Updated)",
        "slug": "test-product-10-updated",
        "price": "35.00",
        "sale_price": "30.00",
        "status": {
            "key": "1",
            "value": "Live"
        },
        "stock_level": 100,
        "stock_status": {
            "key": "1",
            "value": "In Stock"
        },
        "requires_shipping": {
            "key": "1",
            "value": "Yes"
        },
        "description": "Description",
        "sku": "TEST10",
        "category": {
            "id": 16,
            "parent": null,
            "title": "Test Category",
            "slug": "test-category",
            "status": {
                "key": "1",
                "value": "Live"
            },
            "description": "Description"
        },
        "weight": "10.00",
        "width": "10.00",
        "height": "10.00",
        "depth": "10.00",
        "images": [

        ]
    }
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "errors": [
    	"Title must be unique",
        "Slug must be unique"
    ]
}
```
<!--/code-->