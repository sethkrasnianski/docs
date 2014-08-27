<!--
@title Pass a cart to checkout
@author Moltin Ltd
@description Process the checkout data into an order.
@order 4.9

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

When you have collected the data required to process the checkout, you can post it to this endpoint for processing, you can also use the specific endpoints for addresses, orders and order items if you want to process these sections individually. This endpoint will create the addresses, the order and add all the order items. You can then pass this order to the payment endpoint.


#### Resource URL
POST [{{ url }}cart/:identifier/checkout]({{ url }}cart/:identifier/checkout])


#### Parameters
Key | Type | Description
--- | ---- | -----------
customer*optional* | Integer or String | The ID or email address of the customer who is checking out
shipping*optional* | Integer | The ID of the shipping method to use.
gateway | String | The slug of the payment gateway to use.
bill_to | Integer, Array or String | The ID of an existing address, or an array of fields to create a new address. You can also set this to "ship_to" to make the billing address the same as the shipping address.
ship_to | Integer, Array or String | The ID of an existing address, or an array of fields to create a new address. You can also set this to "bill_to" to make the shipping address the same as the billing address.

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": "115",
        "customer": {
            "id": "111",
            "first_name": "Chris",
            "last_name": "Harvey",
            "email": "chris@molt.in"
        },
        "gateway": {
            "name": "Stripe",
            "slug": "stripe",
            "description": null,
            "enabled": true,
            "settings": {
                "apiKey": "my_api_key"
            }
        },
        "status": {
            "key": "unpaid",
            "value": "Unpaid"
        },
        "subtotal": "100.00",
        "shipping_price": "10.00",
        "total": "110.00",
        "currency": {
            "id": 1,
            "code": "GBP",
            "title": "British Pound",
            "enabled": true,
            "modifier": "+0",
            "exchange_rate": "1.00",
            "format": "£{price}",
            "decimal_point": ".",
            "thousand_point": ",",
            "rounding": null,
            "default": false
        },
        "currency_code": "GBP",
        "exchange_rate": "1.00",
        "ship_to": {
            "id": "112",
            "save_as": "",
            "first_name": "Chris",
            "last_name": "Harvey",
            "email": "chris@molt.in",
            "address_1": "55 Moltin Lane",
            "address_2": "",
            "city": "Moltinland",
            "county": "Moltin",
            "postcode": "M01T",
            "country": {
                "code": "GB",
                "name": "United Kingdom"
            },
            "customer": {
                "id": "111",
                "first_name": "Chris",
                "last_name": "Harvey",
                "email": "chris@molt.in"
            },
            "company": "",
            "phone": "123456778"
        },
        "bill_to": {
            "id": "112",
            "save_as": "",
            "first_name": "Chris",
            "last_name": "Harvey",
            "email": "chris@molt.in",
            "address_1": "55 Moltin Lane",
            "address_2": "",
            "city": "Moltinland",
            "county": "Moltin",
            "postcode": "M01T",
            "country": {
                "code": "GB",
                "name": "United Kingdom"
            },
            "customer": {
                "id": "111",
                "first_name": "Chris",
                "last_name": "Harvey",
                "email": "chris@molt.in"
            },
            "company": "",
            "phone": "123456778"
        },
        "shipping": {
            "id": "110",
            "title": "FedEx",
            "slug": "fedex",
            "company": "FedEx",
            "price": "10.00",
            "price_min": "",
            "price_max": "10000.00",
            "weight_min": "",
            "weight_max": "10000.00",
            "description": "",
            "tax_band": {
                "id": 1,
                "title": "Default",
                "description": null,
                "rate": "20.00"
            },
            "status": {
                "key": "1",
                "value": "Live"
            }
        }
    }
}
```
<!--/code-->
