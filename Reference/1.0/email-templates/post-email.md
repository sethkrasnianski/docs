<!--
@title Create new email template
@author Moltin Ltd
@description Creates a new email template

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new email template with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new email template will be returned.


#### Resource URL
POST [{{ api_url }}email]({{ api_url }}email)


#### Parameters
Key | Type | Description
--- | ---- | -----------
slug | String | The Slug/URI of the email template, must be unique
name | String | The name of the email template
subject | String | The subject of the email
url | String | The URL to the email template
secret*optional* | String | A secret key that you can match against when your URL is called
content_type | String | JSON or x-form-urlencoded? json or form
enabled | Boolean | Enabled or Disabled? 1 or 0 

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "slug": "hello",
        "name": "World",
        "subject": "Hello World",
        "url": "http://example.com/",
        "content_type": {
            "value": "application/json",
            "data": {
                "key": "json",
                "value": "application/json"
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


#### Example Failed Response
``` json
{
    "status": false,
    "errors": [
        "The slug field is required.",
        "The name field is required.",
        "The subject field is required.",
        "The url field is required.",
        "The content type field is required.",
        "The enabled field is required."
    ]
}
```
<!--/code-->