<!--
@title GET product
@author Moltin Ltd
@description Gets a product based on the given criteria

@sidebar 1
@family Product 
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a product based on a given set of key-value properties. One or more paramaters can be passed to the method but they must all match exactly and the best match will be returned.

While this call is similar to search it will only return a single product.


#### Resource URL	{#resource}
GET [{{ url }}product]({{ url }}product)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
sku*optional* | String | Select by SKU
title*optional* | String | Select by Title
slug*optional* | String | Select by Slug
price*optional* | Float | Select by Price
sale_price*optional* | Float | Select by Sale Price
status*optional* | Choice (1 or 0) | Select by Status
category*optional* | Integer | Select by Category ID
stock_level*optional* | Integer | Select by Stock Level
stock_status*optional* | Choice (0 to 6) | Select by Stock Status


#### PHP (SDK) Example  {#php}
``` php
    $result = $moltin->get('product', ['slug' => 'test-product-1']);

    if ( ! $result['status'] ) {
        throw new Exception($result['error']);
    }

    $product = $result['result'];
```

<!--code-->
#### Example Successful Response    {#success}
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


#### Example Invalid Response	{#error}
``` json
TBA
```
<!--/code-->