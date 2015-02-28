<!--
@title Get product variation fields
@author Moltin Ltd
@description Gets the flow field data assigned to product variations
@order 3.1.1.2

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product variation creation requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, modifier). It also provides information of field requirements, default values, etc.

#### Resource URL
[{{ api_url }}product/:productId/modifier/:modifierId/variation/fields]({{ api_url }}product/:productId/modifier/:modifierId/variation/fields)

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
            "value": null
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
            "value": null
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
            "value": null
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
            "value": null
        }
    }
}
```

#### PHP (SDK) Example - Direct
``` php
$result = $moltin->get('product/5/modifier/100/variation/fields');
$fields = $result['result'];
```

#### PHP (SDK) Example - Flows Builder
``` php
$fields = $moltin->fields('product/5/modifier/100/variation');
```
<!--/code-->