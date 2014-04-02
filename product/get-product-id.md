<!--
@title Get product by ID
@author Moltin Ltd
@description Returns a product of the given ID
@order 3.3

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call simply returns a product based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
GET [{{ url }}product/:id]({{ url }}product/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 15,
        "title": "Test Product 1",
        "slug": "test-product-1",
        "price": "235.00",
        "sale_price": "200.00",
        "status": {
            "key": "1",
            "value": "Live"
        },
        "stock_level": 234,
        "stock_status": {
            "key": "1",
            "value": "In Stock"
        },
        "requires_shipping": {
            "key": "0",
            "value": "No"
        },
        "description": "This is a test product",
        "sku": "TEST01",
        "category": {
            "id": 18,
            "parent": {
                "id": 17,
                "parent": null,
                "title": "Test Category 1",
                "slug": "test-category-1",
                "status": {
                    "key": "1",
                    "value": "Live"
                },
                "description": "Description"
            },
            "title": "Test Category 2",
            "slug": "test-category-2",
            "status": {
                "key": "1",
                "value": "Live"
            },
            "description": "Description"
        },
        "weight": "100.00",
        "width": "200.00",
        "height": "200.00",
        "depth": "200.00",
        "tax_band": null,
        "pricing":
        {
           "formatted":
           {
               "with_tax": "£235.00",
               "without_tax": "£235.00"
           },
           "rounded":
           {
               "with_tax": 235,
               "without_tax": 235
           },
           "raw":
           {
               "with_tax": 235,
               "without_tax": 235
           }
        },
        "images": {
            "26": {
                "id": 26,
                "name": "product_tablet_landscape.png",
                "url": {
                    "http": "http:\/\/d2xufakadxl3ok.cloudfront.net\/1\/product_tablet_landscape.png",
                    "https": "https:\/\/d2xufakadxl3ok.cloudfront.net\/1\/product_tablet_landscape.png"
                }
            }
        }
    }
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "No product found"
}
```


#### Usage Example
``` php
try {
    $product = $moltin->getProductById(15);
} catch(\Exception $e) {
    exit($e->getMessage());
}
```
<!--/code-->