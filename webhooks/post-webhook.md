<!--
@title Create new webhook
@author Moltin Ltd
@description Creates a new webhook

@sidebar 1
@family Webhooks
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new webhook with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new webhook will be returned.


#### Resource URL
POST [{{ url }}webhook]({{ url }}webhook)


#### Parameters
Key | Type | Description
--- | ---- | -----------
name | String | The name of the webhook
subject | String | The subject of the email
url | String | The URL to the webhook
secret*optional* | String | A secret key that you can match against when your URL is called
content_type | String | JSON or x-form-urlencoded? json or form
create | Integer | Enable on create events? 1 or 0 
update | Integer | Enable on update events? 1 or 0 
delete | Integer | Enable on delete events? 1 or 0 
enabled | Integer | Enabled or Disabled? 1 or 0 

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


### Example Failed Response
``` json
{
    "status": false,
    "errors": [
        "The url field is required.",
        "The content type field is required.",
        "The create field is required.",
        "The update field is required.",
        "The delete field is required.",
        "The enabled field is required."
    ]
}
```
<!--/code-->