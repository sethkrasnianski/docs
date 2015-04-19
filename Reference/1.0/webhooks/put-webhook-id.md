This call edits a webhook with a given id. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ api_url }}webhook/:id]({{ api_url }}webhook/:id)


#### Parameters
Key | Type | Description
--- | ---- | -----------
name*optional* | String | The name of the webhook
subject*optional* | String | The subject of the email
url*optional* | String | The URL to the webhook
secret*optional* | String | A secret key that you can match against when your URL is called
content_type*optional* | String | JSON or x-form-urlencoded? json or form
create*optional* | Boolean | Enable on create events? 1 or 0 
update*optional* | Boolean | Enable on update events? 1 or 0 
delete*optional* | Boolean | Enable on delete events? 1 or 0 
enabled*optional* | Boolean | Enabled or Disabled? 1 or 0 

<!--code-->
#### Example Successful Response 
``` json
{
    "status": true,
    "result": {
        "id": "7aa8ad0d-69ea-419a-a4c3-fe8ee69fc2b8",
        "url": "http://demo.molt.in/test2.php",
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


#### Example Error Response 
``` json
{
    "status": false,
    "errors": [
        "The selected enabled is invalid."
    ]
}
```
<!--/code-->