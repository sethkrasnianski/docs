<!--
@title Get a specific product modifiers fields
@author Moltin Ltd
@description Gets the given product modifiers flow data and field fields
@order 3.1.3

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product edit requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Product). It also provides information of field requirements, default values, etc.

Unlike /product/:id/modifier/fields this adds the current modifiers data to the array to allow for prepopulation of fields.

#### Resource URL
[{{ url }}product/:productId/modifier/:id/fields]({{ url }}product/:productId/modifier/:id/fields)

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
           "value":
           {
               "value": "Variant",
               "data":
               {
                   "key": "variant",
                   "value": "Variant"
               }
           }
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
           "value": "Colour"
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
           "value": "Please select a colour"
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
           "value": 6
       }
   }
}
```
<!--/code-->