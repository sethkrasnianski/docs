<!--
@title Get a specific product variation fields
@author Moltin Ltd
@description Gets the given product variation flow data and field fields
@order 3.1.1.3

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product edit requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Modifier). It also provides information of field requirements, default values, etc.

Unlike /products/:id/modifiers/fields this adds the current variation data to the array to allow for prepopulation of fields.

#### Resource URL
[{{ api_url }}products/:productId/modifiers/:id/fields]({{ api_url }}products/:productId/modifiers/:id/fields)

#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "title":
        {
            "slug": "title",
            "name": "Title",
            "type": "string",
            "options":
            [
            ],
            "required": true,
            "unique": false,
            "locked": true,
            "order": null,
            "value": "Red"
        },
        "mod_price":
        {
            "slug": "mod_price",
            "name": "Price Modifier",
            "type": "string",
            "options":
            [
            ],
            "required": false,
            "unique": false,
            "locked": true,
            "order": null,
            "value": "-0.50"
        },
        "modifier":
        {
            "slug": "modifier",
            "name": "Parent",
            "type": "integer",
            "options":
            {
                "default": 0
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null,
            "value": 523
        },
        "product":
        {
            "slug": "product",
            "name": "Product",
            "type": "integer",
            "options":
            {
                "default": 0
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null,
            "value": 0
        }
    }
}
```
<!--/code-->