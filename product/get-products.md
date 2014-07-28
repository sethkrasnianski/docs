<!--
@title Get multiple products by criteria
@author Moltin Ltd
@description Gets a list of products based on the given criteria
@order 3.5

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of products based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ url }}products]({{ url }}products)


#### parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of products to return
offset*optional* | Integer | The first product to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
            "id": 14,
            "title": "Test Product 03",
            "slug": "test-product-03",
            "price": "250.00",
            "sale_price": "135.00",
            "status": {
                "key": "0",
                "value": "Draft"
            },
            "stock_level": 34,
            "stock_status": {
                "key": "1",
                "value": "In Stock"
            },
            "requires_shipping": {
                "key": "0",
                "value": "No"
            },
            "description": "Description",
            "sku": "TEST03",
            "category": null,
            "weight": "250.00",
            "width": "100.00",
            "height": "100.00",
            "depth": "100.00",
            "tax_band": null,
            "pricing":
            {
               "formatted":
               {
                   "with_tax": "£250.00",
                   "without_tax": "£250.00"
               },
               "rounded":
               {
                   "with_tax": 250,
                   "without_tax": 250
               },
               "raw":
               {
                   "with_tax": 250,
                   "without_tax": 250
               }
            },
            "images": [

            ]
        },
        {
            "id": 15,
            "title": "Test Product 02",
            "slug": "test-product-02",
            "price": "235.00",
            "sale_price": "200.00",
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
                "key": "0",
                "value": "No"
            },
            "description": "Description",
            "sku": "TEST02",
            "category": {
                "id": 18,
                "parent": {
                    "id": 17,
                    "parent": null,
                    "title": "Test Category 01",
                    "slug": "test-category-01",
                    "status": {
                        "key": "1",
                        "value": "Live"
                    },
                    "description": "Description"
                },
                "title": "Test Category 02",
                "slug": "test-category-02",
                "status": {
                    "key": "1",
                    "value": "Live"
                },
                "description": "Desc"
            },
            "weight": "100.00",
            "width": "100.00",
            "height": "100.00",
            "depth": "100.00",
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
        },
        {
            "id": 10,
            "title": "Test Product 01",
            "slug": "test-product-01",
            "price": "135.00",
            "sale_price": "100.00",
            "status": {
                "key": "1",
                "value": "Live"
            },
            "stock_level": 55,
            "stock_status": {
                "key": "1",
                "value": "In Stock"
            },
            "requires_shipping": {
                "key": "0",
                "value": "No"
            },
            "description": "Description",
            "sku": "TEST01",
            "category": null,
            "weight": "5.00",
            "width": "3.00",
            "height": "4.00",
            "depth": "2.00",
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
    ],
    "pagination": {
        "total": 9,
        "current": 3,
        "limit": 3,
        "offset": 0,
        "from": 1,
        "to": 3,
        "offsets": {
            "first": 0,
            "previous": false,
            "next": 3,
            "last": 6
        },
        "links": {
            "first": "https:\/\/api.molt.in\/beta\/products?limit=3",
            "previous": false,
            "next": "https:\/\/api.molt.in\/beta\/products?offset=3&limit=3",
            "last": "https:\/\/api.molt.in\/beta\/products?offset=6&limit=3"
        }
    }
}
```


#### Example Empty Response
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
            "first": "https:\/\/api.molt.in\/beta\/products?limit=3",
            "previous": "https:\/\/api.molt.in\/beta\/products?offset=7&limit=3",
            "next": false,
            "last": "https:\/\/api.molt.in\/beta\/products?offset=6&limit=3"
        }
    }
}
```
<!--/code-->