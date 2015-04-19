This call creates a new category with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new category will be returned.

#### Resource URL
POST [{{ api_url }}categories]({{ api_url }}categories)

#### Parameters
Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | ------ | -------
Parent Category | parent | Relationship | No | No | Relates to [Categories](categories).
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Title | title | String | Yes | No | -
Description | description | Text | Yes | No | -


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
    }
}
```
<!--/code-->
