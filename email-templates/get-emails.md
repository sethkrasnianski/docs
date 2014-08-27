<!--
@title Get multiple email templates by criteria
@author Moltin Ltd
@description Gets an array of email templates

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a list of email templates that have been setup.


#### Resource URL
GET [{{ url }}emails]({{ url }}emails)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
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
        },
        {
            "name": "Order Dispatched",
            "subject": "Your order has been dispatched",
            "slug": "order_dispatched",
            "url": "http://molt.in/templates/order_dispatched.html",
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
    ],
    "pagination": {
        "total": 2,
        "current": 2,
        "limit": 10,
        "offset": 0,
        "from": 1,
        "to": 2,
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