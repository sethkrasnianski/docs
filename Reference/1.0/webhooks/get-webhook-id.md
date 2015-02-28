Returns a webhook based on a given id.


#### Resource URL
[{{ api_url }}webhook/:id]({{ api_url }}webhook/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": "7aa8ad0d-69ea-419a-a4c3-fe8ee69fc2b8",
        "url": "http://demo.molt.in/test.php",
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
}
```


#### Example Not Found Response
``` json
{
  "status": false,
  "error": "Webhook not found"
}
```
<!--/code-->