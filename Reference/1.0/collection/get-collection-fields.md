This call returns the data required to build a dynamic flows form based on the collection creation requirements. It provides all options available for the choice fields as well as those featured in relationships. It also provides information of field requirements, default values, etc.

#### Resource URL
[{{ api_url }}collections/fields]({{ api_url }}collections/fields)


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
        }
    }
}
```
<!--/code-->