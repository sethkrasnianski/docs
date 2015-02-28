This call returns a range of products based on the various provided search criteria. Using limit and offset you can also paginate the results.


#### Resource URL
GET [{{ api_url }}products/search]({{ api_url }}products/search)


#### Parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of products to return
offset*optional* | Integer | The first product to be shown, used for pagination
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


#### Example Invalid Response
``` json
{
    "status": true,
    "result": [

    ],
    "pagination": {
        "total": 9,
        "current": 0,
        "limit": 3,
        "offset": 10,
        "from": 11,
        "to": 10,
        "offsets": {
            "first": 0,
            "previous": 7,
            "next": false,
            "last": 6
        },
        "links": {
            "first": "https:\/\/api.molt.in\/beta\/products/search?limit=3",
            "previous": "https:\/\/api.molt.in\/beta\/products/search?offset=7&limit=3",
            "next": false,
            "last": "https:\/\/api.molt.in\/beta\/products/search?offset=6&limit=3"
        }
    }
}
```
<!--/code-->