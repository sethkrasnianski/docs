This call returns the data required to build a dynamic flows form based on the brand creation requirements. It provides all options available for the choice fields as well as those featured in relationships. It also provides information of field requirements, default values, etc.

#### Resource URL
[{{ api_url }}brands/fields]({{ api_url }}brands/fields)


#### Parameters
None required

<!--code-->
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
      "order": 1
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
      "order": 2
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
      "order": 3
    },
    "description": {
      "slug": "description",
      "name": "Description",
      "type": "text",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 4
    }
  }
}
```
<!--/code-->
