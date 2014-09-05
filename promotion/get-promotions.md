<!--
@title Get a list of promotions
@author Moltin Ltd
@description Gets a list of promotions
@order 3.5

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a list of promotions. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ url }}/promotions/cart]({{ url }}/promotions/cart)


#### Parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of promotions to return
offset*optional* | Integer | The first promotion to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
            "id": 306,
            "title": "50% off",
            "description": "",
            "from": "2014-01-01",
            "to": "2015-01-01",
            "discount_code": "",
            "max_uses": 0,
            "customer_uses": 0,
            "customer_group": null,
            "status": {
                "value": "Enabled",
                "data": {
                    "key": "1",
                    "value": "Enabled"
                }
            },
            "terminating": {
                "value": "Yes",
                "data": {
                    "key": "1",
                    "value": "Yes"
                }
            },
            "persistent": {
                "value": "No",
                "data": {
                    "key": "0",
                    "value": "No"
                }
            },
            "action": {
                "value": "Discount cart subtotal by percentage",
                "data": {
                    "key": "discount_subtotal_percent",
                    "value": "Discount cart subtotal by percentage"
                }
            },
            "priority": 0,
            "amount": 50,
            "max_quantity": 0,
            "trigger_quantity": 0,
            "apply_to_shipping": {
                "value": "No",
                "data": {
                    "key": "0",
                    "value": "No"
                }
            },
            "shipping_methods": null,
            "created_at": "2014-06-05 13:23:30",
            "updated_at": "2014-06-05 13:23:30",
            "match_rules": {
                "type": "group",
                "operator": "=",
                "match": "",
                "against": "",
                "children": [
                    {
                        "type": "cart_item",
                        "operator": "=",
                        "match_on": "any",
                        "match": "price",
                        "against": 100
                    }
                ],
                "match_on": "any"
            },
            "match_items": null
        }
    ],
    "pagination": {
        "total": 1,
        "current": 1,
        "limit": 15,
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


#### Example Empty Response
``` json
{
    "status": true,
    "result": [],
    "pagination": {
        "total": 0,
        "current": 0,
        "limit": 15,
        "offset": 0,
        "from": false,
        "to": false,
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