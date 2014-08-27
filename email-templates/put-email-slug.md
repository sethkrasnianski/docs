<!--
@title Update an email template
@author Moltin Ltd
@description Updates an email template with the given slug

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits an email template with a given slug. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL {#resource}
PUT [{{ url }}email/:slug]({{ url }}email/:slug)


#### Parameters {#parameters}
Key | Type | Description
--- | ---- | -----------
slug*optional* | String | The Slug/URI of the email template, must be unique
name*optional* | String | The name of the email template
subject*optional* | String | The subject of the email
url*optional* | String | The URL to the email template
secret*optional* | String | A secret key that you can match against when your URL is called
content_type*optional* | String | JSON or x-form-urlencoded? json or form
enabled*optional* | String | Enabled or Disabled? 1 or 0 

<!--code-->
#### Example Successful Response  {#success}
``` json
{
    "status": true,
    "result": {
        "name": "World2",
        "subject": "Hello World",
        "slug": "hello",
        "url": "http://example.com/",
        "content_type": {
            "value": "application/json",
            "data": {
                "key": "json",
                "value": "application/json"
            }
        },
        "secret": null,
        "enabled": {
            "value": "Yes",
            "data": {
                "key": 1,
                "value": "Yes"
            }
        },
        "locked": {
            "value": "No",
            "data": {
                "key": 0,
                "value": "No"
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