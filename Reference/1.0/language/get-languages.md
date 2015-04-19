Returns a list of languages that have been setup. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ api_url }}languages]({{ api_url }}languages)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
            "id": "934330576867951337",
            "order": null,
            "created_at": "2015-03-06 00:16:42",
            "updated_at": "2015-03-06 00:16:42",
            "title": "French",
            "code": "french",
            "status": {
                "value": "Live",
                "data": {
                    "key": "1",
                    "value": "Live"
                }
            }
        },
        {
            "id": "934330689954775786",
            "order": null,
            "created_at": "2015-03-06 00:16:55",
            "updated_at": "2015-03-06 00:16:55",
            "title": "Spanish",
            "code": "spanish",
            "status": {
                "value": "Live",
                "data": {
                    "key": "1",
                    "value": "Live"
                }
            }
        },
        {
            "id": "934330840203133675",
            "order": null,
            "created_at": "2015-03-06 00:17:13",
            "updated_at": "2015-03-06 00:17:13",
            "title": "German",
            "code": "german",
            "status": {
                "value": "Live",
                "data": {
                    "key": "1",
                    "value": "Live"
                }
            }
        }
    ],
    "pagination": {
        "total": 3,
        "current": 3,
        "limit": 10,
        "offset": 0,
        "from": 1,
        "to": 3,
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
        },
        "currentFilters": [],
        "currentPage": 1,
        "paginationPath": "language",
        "lastPage": 1,
        "extremePagesLimit": 2,
        "nearbyPagesLimit": 4
    }
}
```


#### Example Empty Response
``` json
{
  "status": true,
  "result": [],
  "pagination": {
    "total": 0,
    "current": 0,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 0,
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