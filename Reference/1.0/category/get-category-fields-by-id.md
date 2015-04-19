This call returns the data required to build a dynamic flows form based on the category edit requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Parent). It also provides information of field requirements, default values, etc.

Unlike /categories/fields this adds the current products data to the array to allow for prepopulation of fields.

#### Resource URL
GET [{{ api_url }}categories/:id/fields]({{ api_url }}categories/:id/fields)

<!--code-->
``` json
{
    "status": true,
    "result": {
        "parent": {
            "slug": "parent",
            "name": "Parent Category",
            "type": "relationship",
            "options": {
                "relates_to": 4
            },
            "required": false,
            "unique": false,
            "locked": true,
            "order": null,
            "instructions": null,
            "available": {
                "959732764679078722": "Uncategorized",
                "959873227918672743": "Test Category"
            },
            "value": null
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
            "order": null,
            "instructions": null,
            "value": "test-category"
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
            "order": null,
            "instructions": null,
            "value": {
                "value": "Live",
                "data": {
                    "key": "1",
                    "value": "Live"
                }
            }
        },
        "title": {
            "slug": "title",
            "name": "Title",
            "type": "string",
            "options": {
                "multilingual": true
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null,
            "instructions": null,
            "value": "Test Category"
        },
        "description": {
            "slug": "description",
            "name": "Description",
            "type": "text",
            "options": {
                "multilingual": true,
                "wysiwyg": false
            },
            "required": true,
            "unique": false,
            "locked": true,
            "order": null,
            "instructions": null,
            "value": "My first category"
        }
    }
}
```
<!--/code-->
