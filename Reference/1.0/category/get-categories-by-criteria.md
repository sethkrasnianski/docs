Returns a range of categories based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ api_url }}categories]({{ api_url }}categories)

#### Parameters
Name | Key | Type | Details
---- | --- | ---- | ------
Parent Category | parent | Relationship | Relates to [Categories](categories).
Slug | slug | Slug | A unique identifier generally used as part of a URL.
Status | status | Choice | Choices available are 0 (Draft), 1 (Live).
Title | title | String | -
Description | description | Text | -
Limit | limit | Integer | Number of entries to return
Offset | offset | Integer | Number of entries to skip


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
    "pagination": {
        "total": 2,
        "current": 2,
        "limit": 10,
        "offset": 0,
        "from": 1,
        "to": 2,
        "offsets": {
            "first": false,
            "previous": false,
            "next": false,
            "last": false
        },
        "links": {
            "first": false,
            "previous": false,
            "next": false,
            "last": false
        }
    }
}
```
<!--/code-->
