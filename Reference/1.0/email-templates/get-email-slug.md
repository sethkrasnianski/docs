<!--
@title Get email template by slug
@author Moltin Ltd
@description Returns an email template of the given slug

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns an email template based on a given slug.


#### Resource URL
[{{ api_url }}email/:slug]({{ api_url }}email/:slug)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "name": "Order Paid",
        "subject": "Your payment has been processed",
        "slug": "order_paid",
        "url": "http://molt.in/templates/order_paid.html",
        "content_type": {
            "value": "application/x-www-form-urlencoded",
            "data": {
                "key": "form",
                "value": "application/x-www-form-urlencoded"
            }
        },
        "secret": null,
        "enabled": {
            "value": "No",
            "data": {
                "key": 0,
                "value": "No"
            }
        },
        "locked": {
            "value": "Yes",
            "data": {
                "key": 1,
                "value": "Yes"
            }
        }
    }
}
```


#### Example Empty Response
``` json
{
  "status": false,
  "error": "Email template not found"
}
```
<!--/code-->