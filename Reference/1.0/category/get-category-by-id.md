Returns a category based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.

#### Resource URL
GET [{{ api_url }}categories/:id]({{ api_url }}categories/:id)

<!--code-->
``` json
{
    "status": true,
    "result": {
        "id": "959873227918672743",
        "order": null,
        "created_at": "2015-04-10 06:02:42",
        "updated_at": "2015-04-10 06:02:42",
        "parent": null,
        "slug": "test-category",
        "status": {
            "value": "Live",
            "data": {
                "key": "1",
                "value": "Live"
            }
        },
        "title": "Test Category",
        "description": "My first category",
        "images": []
    },
    "pagination": {
        "items": {
            "previous": false,
            "next": false
        }
    }
}
```
<!--/code-->
