This call edits a category with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.

#### Resource URL
PUT [{{ api_url }}categories/:id]({{ api_url }}categories/:id)

#### Parameters
Name | Key | Type | Unique | Details
---- | --- | ---- | ------ | -------
Parent Category | parent | Relationship | No | Relates to [Categories](categories).
Slug | slug | Slug | Yes | A unique identifier generally used as part of a URL.
Status | status | Choice | No | Choices available are 0 (Draft), 1 (Live).
Title | title | String | No | -
Description | description | Text | No | -


<!--code-->
``` json
{
    "status": true,
    "result": {
        "id": "959873227918672743",
        "order": null,
        "created_at": "2015-04-10 06:02:42",
        "updated_at": "2015-04-10 06:02:44",
        "parent": null,
        "slug": "test-category",
        "status": {
            "value": "Live",
            "data": {
                "key": "1",
                "value": "Live"
            }
        },
        "title": "Test category (Updated)",
        "description": "My first category",
        "images": []
    }
}
```
<!--/code-->
