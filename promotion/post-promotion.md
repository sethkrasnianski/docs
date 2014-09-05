<!--
@title Create new promotion
@author Moltin Ltd
@description Creates a new promotion
@order 3.1

@sidebar 1
@family Promotion
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new promotion with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new promotion will be returned.

#### Resource URL
POST [{{ url }}promotion/cart]({{ url }}promotion/cart)


#### Parameters
Key | Type | Description
--- | ---- | -----------
sku | String | The SKU of the promotion, must be unique
title | String | The Title of the promotion, must be unique
from | Datetime | The start date of the promotion
to | Datetime |  The end date of the promotion
status | Boolean | The status of the promotion
terminating | Boolean | Whether the rule terminates after the first catch
action | Choice (buy_x_get_y_free, discount_by_fixed, discount_by_percent, discount_to_fixed, discount_subtotal_fixed, discount_subtotal_percent)
amount | Integer | The amount to discount
apply_to_shipping | Boolean | Whether the discount will apply to shipping
persistent | Boolean | *******

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 422,
        "title": "Buy one get one free",
        "description": "",
        "from": "2014-05-05",
        "to": "2015-05-05",
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
            "value": "No",
            "data": {
                "key": "0",
                "value": "No"
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
            "value": "Discount items by percentage",
            "data": {
                "key": "discount_by_percent",
                "value": "Discount items by percentage"
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
        "created_at": "2014-09-05 15:32:13",
        "updated_at": "2014-09-05 15:32:13",
        "match_rules": null,
        "match_items": null
    }
}
```


#### Example Invalid ID Response
``` json
{
    "status": false,
    "errors": [
        "Title is required",
        "From Date is required",
        "To Date is required",
        "Status is required",
        "Terminate processing further promotions? is required",
        "Persist if terminated? is required",
        "Action is required",
        "Discount Amount is required",
        "Apply discount to shipping is required"
    ]
}
```
<!--/code-->