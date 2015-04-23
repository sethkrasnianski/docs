This call creates a new product with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new product will be returned.

#### Resource URL
POST [{{ api_url }}product]({{ api_url }}product)


#### Parameters
Key | Type | Description
--- | ---- | -----------
sku | String | The SKU of the product, must be unique
title | String | The Title of the product, must be unique
slug | String | The Slug/URI of the product, must be unique
price | Float | The Price of the product
status | Choice (1 or 0) | Is the product Live or a Draft
category | Integer | The Category of the product
stock_level | Integer | The Stock Level of the product
stock_status | Choice (0 to 5) | The Stock Status of the product
description | String | The Description of the product
requires_shipping | Choice (1 or 0) | Does the product require Shipping?
sale_price*optional* | Float | The Sale Price of the product
weight*optional* | Float | The Weight of the product, used in shipping calculations
height*optional* | Float | The Height of the product, used in shipping calculations
width*optional* | Float | The Width of the product, used in shipping calculations
depth*optional* | Float | The Depth of the product, used in shipping calculations


#### Stock Status
Value | Title
--- | ----
0 | Unlimited
1 | In Stock
2 | Low Stock
3 | Out of Stock
4 | More Stock Ordered
5 | Discontinued


<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 26,
        "title": "Test Product 10",
        "slug": "test-product-10",
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
        "tax_band": null,
        "pricing":
        {
           "formatted":
           {
               "with_tax": "£35.00",
               "without_tax": "£35.00"
           },
           "rounded":
           {
               "with_tax": 35,
               "without_tax": 35
           },
           "raw":
           {
               "with_tax": 35,
               "without_tax": 35
           }
        },
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
        "Slug must be unique",
        "SKU is required",
        "Category is required"
    ]
}
```
<!--/code-->
