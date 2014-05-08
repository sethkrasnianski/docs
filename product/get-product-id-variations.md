<!--
@title Get product variations
@author Moltin Ltd
@description Returns a list of child-product variations of the given product
@order 3.5

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of child-product variations for a product. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ url }}product/:id/variations]({{ url }}product/:id/variations)

#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    [
        {
            "id": "525",
            "sku": "PRD_A0002_RESMRE",
            "title": "Conté Sticks - Red Small Red",
            "slug": "conte-sticks-red-small-red",
            "price": "8.49",
            "sale_price": "8.99",
            "status":
            {
                "value": "Live",
                "data":
                {
                    "key": "1",
                    "value": "Live"
                }
            },
            "category":
            {
                "value": "Arts and Crafts",
                "data":
                {
                    "42":
                    {
                        "id": "42",
                        "parent": null,
                        "title": "Arts and Crafts",
                        "slug": "arts-and-crafts",
                        "status":
                        {
                            "value": "Live",
                            "data":
                            {
                                "key": "1",
                                "value": "Live"
                            }
                        },
                        "description": "Good quality art materials at affordable prices. We're here to help you create without limits!",
                        "created_at": "",
                        "updated_at": ""
                    }
                }
            },
            "stock_level": 1050,
            "stock_status":
            {
                "value": "In Stock",
                "data":
                {
                    "key": "1",
                    "value": "In Stock"
                }
            },
            "description": "Drawing with conté sticks is a sure way to achive high contrast, richly pigmented images. This media can also be usto shapen lines as a final stage of a painting's development. ",
            "requires_shipping":
            {
                "value": "Yes",
                "data":
                {
                    "key": "1",
                    "value": "Yes"
                }
            },
            "weight": "10.00",
            "height": "10.00",
            "width": "10.00",
            "depth": "10.00",
            "collection": null,
            "brand":
            {
                "value": " ",
                "data":
                {
                    "id": "514",
                    "title": " ",
                    "slug": " ",
                    "status":
                    {
                        "value": "Draft",
                        "data":
                        {
                            "key": "0",
                            "value": "Draft"
                        }
                    },
                    "description": " ",
                    "created_at": "2014-05-06 15:59:43",
                    "updated_at": "2014-05-06 15:59:43"
                }
            },
            "tax_band": null,
            "meta_title": "",
            "created_at": "2014-05-07 10:58:03",
            "updated_at": "2014-05-07 11:03:26",
            "pricing":
            {
                "formatted":
                {
                    "with_tax": "£8.49",
                    "without_tax": "£8.49"
                },
                "rounded":
                {
                    "with_tax": 8.49,
                    "without_tax": 8.49
                },
                "raw":
                {
                    "with_tax": 8.49,
                    "without_tax": 8.49
                }
            },
            "is_variation": true,
            "modifiers":
            [
                {
                    "data":
                    {
                        "type": "variant",
                        "title": "Colour",
                        "product": "6",
                        "instructions": "Please select a colour"
                    },
                    "var_title": "Red",
                    "var_price": null,
                    "var_id": 451
                },
                {
                    "data":
                    {
                        "type": "variant",
                        "title": "Size",
                        "product": "6",
                        "instructions": "Please select a size"
                    },
                    "var_title": "Small",
                    "var_price": null,
                    "var_id": 458
                },
                {
                    "data":
                    {
                        "type": "variant",
                        "title": "Colour",
                        "product": "6",
                        "instructions": "Updated instructions"
                    },
                    "var_title": "Red",
                    "var_price": null,
                    "var_id": 524
                }
            ],
            "images":
            {
                "45":
                {
                    "id": 45,
                    "name": "artpastels1.jpg",
                    "url":
                    {
                        "http": "http://d2xufakadxl3ok.cloudfront.net/1/artpastels1.jpg",
                        "https": "https://d2xufakadxl3ok.cloudfront.net/1/artpastels1.jpg"
                    }
                },
                "47":
                {
                    "id": 47,
                    "name": "artpastels2.jpg",
                    "url":
                    {
                        "http": "http://d2xufakadxl3ok.cloudfront.net/1/artpastels2.jpg",
                        "https": "https://d2xufakadxl3ok.cloudfront.net/1/artpastels2.jpg"
                    }
                }
            }
        }
        [...]
    ]
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "No products found"
}
```

#### Usage Example
``` php
try {
    $products = $moltin->get('product/6/variations');
} catch(\Exception $e) {
    exit($e->getMessage());
}
```
<!--/code-->