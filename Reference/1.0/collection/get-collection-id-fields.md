This call returns the data required to build a dynamic flows form based on the product edit requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Categories). It also provides information of field requirements, default values, etc.

Unlike /products/fields this adds the current products data to the array to allow for prepopulation of fields.

#### Resource URL
[{{ api_url }}collections/:id/fields]({{ api_url }}collections/:id/fields)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "title": {
      "slug": "title",
      "name": "Collection Title",
      "type": "string",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 1,
      "value": "Sofas Range"
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
      "order": 2,
      "value": "sofas-range"
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
      "order": 3,
      "value": {
        "key": "1",
        "value": "Live"
      }
    },
    "description": {
      "slug": "description",
      "name": "Description",
      "type": "text",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 3,
      "value": "My collection of products"
    }
  }
}
```
<!--/code-->