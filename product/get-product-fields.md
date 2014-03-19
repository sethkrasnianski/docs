<!--
@title GET products/fields
@author Moltin Ltd
@description Gets the flow field data assigned to products
@order 3.7

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product creation requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Categories). It also provides information of field requirements, default values, etc.

#### Resource URL
[{{ url }}products/fields]({{ url }}products/fields)


#### Paramaters
None required


#### PHP (SDK) Example - Direct  {#php}
``` php
    $result      = $moltin->get('product/fields');
    $fields = $result['result'];
```


#### PHP (SDK) Example - Flows Builder
Built in to the PHP SDK is a form builder that can automatically generate the HTML form elements for you as well as make the necissary calls.
``` php
    $fields = $moltin->fields('product');
```

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "title": {
            "slug": "title",
            "name": "Product Title",
            "type": "string",
            "options": [

            ],
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "slug": {
            "slug": "slug",
            "name": "Slug",
            "type": "slug",
            "options": {
                "parent": "title"
            },
            "required": true,
            "unique": true,
            "locked": true,
            "order": null
        },
        "price": {
            "slug": "price",
            "name": "Price",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "sale_price": {
            "slug": "sale_price",
            "name": "Sale Price",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": false,
            "unique": false,
            "locked": false,
            "order": null
        },
        "status": {
            "slug": "status",
            "name": "Status",
            "type": "choice",
            "options": {
                "choices": [
                    "Draft",
                    "Live"
                ],
                "default": 0
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "stock_level": {
            "slug": "stock_level",
            "name": "Stock Level",
            "type": "integer",
            "options": {
                "default": false
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "stock_status": {
            "slug": "stock_status",
            "name": "Stock Status",
            "type": "choice",
            "options": {
                "choices": [
                    "Unlimited",
                    "In Stock",
                    "Low Stock",
                    "Out Of Stock",
                    "More Stock Ordered",
                    "Discontinued"
                ],
                "default": 1
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "requires_shipping": {
            "slug": "requires_shipping",
            "name": "Requires Shipping",
            "type": "choice",
            "options": {
                "choices": [
                    "No",
                    "Yes"
                ],
                "default": 1
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "description": {
            "slug": "description",
            "name": "Description",
            "type": "text",
            "options": [

            ],
            "required": true,
            "unique": false,
            "locked": true,
            "order": null
        },
        "sku": {
            "slug": "sku",
            "name": "SKU",
            "type": "string",
            "options": [

            ],
            "required": true,
            "unique": true,
            "locked": true,
            "order": null
        },
        "category": {
            "slug": "category",
            "name": "Category",
            "type": "relationship",
            "options": [

            ],
            "required": true,
            "unique": false,
            "locked": true,
            "order": null,
            "available": {
                "19": "Test Category 4",
                "17": "Test Category 7",
                "16": "Test Category",
                "18": "Test Category 3"
            }
        },
        "weight": {
            "slug": "weight",
            "name": "Weight",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null
        },
        "width": {
            "slug": "width",
            "name": "Width",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null
        },
        "height": {
            "slug": "height",
            "name": "Height",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null
        },
        "depth": {
            "slug": "depth",
            "name": "Depth",
            "type": "decimal",
            "options": {
                "decimal_places": 2
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null
        }
    }
}
```
<!--/code-->