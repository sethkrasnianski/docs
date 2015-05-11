This call returns the data required to build a dynamic flows form based on the brand edit requirements. It provides all options available for the choice fields as well as those featured in relationships. It also provides information of field requirements, default values, etc.

Unlike /brands/fields this adds the current brands data to the array to allow for prepopulation of fields.

#### Resource URL
[{{ api_url }}brands/:id/fields]({{ api_url }}brands/:id/fields)


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
      "name": "Brand Title",
      "type": "string",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 1,
      "value": "Moltin"
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
      "value": "moltin"
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
      "order": 4,
      "value": "The moltin brand"
    }
  }
}
```
<!--/code-->