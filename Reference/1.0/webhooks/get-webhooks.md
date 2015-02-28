Returns a list of webhooks that have been setup.


#### Resource URL
GET [{{ api_url }}webhooks]({{ api_url }}webhooks)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
            "id": "7aa8ad0d-69ea-419a-a4c3-fe8ee69fc2b8",
            "url": "http://example.com/my_webhook_handler",
            "content_type": {
                "value": "application/x-www-form-urlencoded",
                "data": {
                    "key": "form",
                    "value": "application/x-www-form-urlencoded"
                }
            },
            "secret": null,
            "create": {
                "value": "Yes",
                "data": {
                    "key": 1,
                    "value": "Yes"
                }
            },
            "update": {
                "value": "Yes",
                "data": {
                    "key": 1,
                    "value": "Yes"
                }
            },
            "delete": {
                "value": "Yes",
                "data": {
                    "key": 1,
                    "value": "Yes"
                }
            },
            "enabled": {
                "value": "Yes",
                "data": {
                    "key": 1,
                    "value": "Yes"
                }
            }
        }
    ],
    "pagination": {
        "total": 1,
        "current": 1,
        "limit": 10,
        "offset": 0,
        "from": 1,
        "to": 1,
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