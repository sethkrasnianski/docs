<!--
@title Get product modifier fields
@author Moltin Ltd
@description Gets the flow field data assigned to product modifiers
@order 3.1.2

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product modifier creation requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, product). It also provides information of field requirements, default values, etc.

#### Resource URL
[{{ api_url }}products/:productId/modifiers/fields]({{ api_url }}products/:productId/modifiers/fields)

#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
   "status": true,
   "result":
   {
       "type":
       {
           "slug": "type",
           "name": "Type",
           "type": "choice",
           "options":
           {
               "choices":
               {
                   "variant": "Variant",
                   "single": "Single",
                   "input": "Input"
               },
               "default": "variant"
           },
           "required": true,
           "unique": false,
           "locked": true,
           "order": null,
           "value": null
       },
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
       "instructions":
       {
           "slug": "instructions",
           "name": "Instructions",
           "type": "text",
           "options":
           [
           ],
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
$result = $moltin->get('product/5/modifier/fields');
$fields = $result['result'];
```

#### PHP (SDK) Example - Flows Builder
``` php
$fields = $moltin->fields('product/5/modifier');
```
<!--/code-->