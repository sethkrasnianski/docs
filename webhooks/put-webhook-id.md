<!--
@title Update an webhook
@author Moltin Ltd
@description Updates an webhook with the given id

@sidebar 1
@family Webhooks
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a webhook with a given id. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL {#resource}
PUT [{{ url }}webhook/:id]({{ url }}webhook/:id)


#### Parameters {#parameters}
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
#### Example Successful Response  {#success}
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


### Example Error Response  {#error}
``` json
{
    "status": false,
    "errors": [
        "The selected enabled is invalid."
    ]
}
```
<!--/code-->