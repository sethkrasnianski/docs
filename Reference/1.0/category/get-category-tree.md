Returns a full structured categories based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ api_url }}categories/tree]({{ api_url }}categories/tree)

<!--code-->
``` json
{
    "status": true,
    "result": [
        {
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
        }
    ],
    "pagination": null
}
```
<!--/code-->
