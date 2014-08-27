<!--
@title Add variation to cart
@author Moltin Ltd
@description Insert a variation into the cart
@order 4.2

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

You can insert a product variation into the cart by POSTing to the cart endpoint with a list of parameters and modifier/variation pairs.

#### Resource URL
POST [{{ url }}cart/[:identifier]]({{ url }}cart/[:identifier])

#### Parameters
Key | Type | Description
--- | ---- | -----------
modifier | Array | Modifier key pairs, modifier[:modifierId]=:variationId, eg modifier[401]=402
quantity | Integer | How many of this product you want to add to the cart

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "item":
    {
        "identifier": "007297ed53cdc06b2a895f93190f1281",
        "modifier":
        {
            "523": "524"
        },
        "quantity": "3",
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
        "description": "Drawing with conté sticks is a sure way to achive high contrast, richly pigmented images. This media can also be used to shapen lines as a final stage of a painting's development. ",
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
                "without_tax": "£8.49",
                "tax": "£0.00"
            },
            "rounded":
            {
                "with_tax": 8.49,
                "without_tax": 8.49,
                "tax": 0
            },
            "raw":
            {
                "with_tax": 8.49,
                "without_tax": 8.49,
                "tax": 0
            }
        },
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
        },
        "name": "Conté Sticks - Red Small Red",
        "total": 25.47,
        "total_before_tax": 25.47,
        "totals":
        {
            "formatted":
            {
                "with_tax": "£25.47",
                "without_tax": "£25.47",
                "tax": "£0.00"
            },
            "rounded":
            {
                "with_tax": 25.47,
                "without_tax": 25.47,
                "tax": 0
            },
            "raw":
            {
                "with_tax": 25.47,
                "without_tax": 25.47,
                "tax": 0
            }
        }
    }
}
```

#### Example Failed Response
``` json
{
  "status": false,
  "error": "The variation was not found"
}
```
<!--/code-->