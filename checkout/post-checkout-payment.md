<!--
@title Process payment for an order
@author Moltin Ltd
@description Process the payment for an order.
@order 13.1

@sidebar 1
@family Checkout
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

When you have an order that is ready to be processed, you can call this method to process the payment. Payment gateways come in two forms, on-site gateways like Stripe where the card information is taken on your site then passed through to the gateway, and off-site gateways like PayPal that redirect the user to the gateway to process the payment.


#### Resource URL
POST [{{ url }}checkout/payment/:method/:orderId]({{ url }}checkout/payment/:method/:orderId])

#### Payment Methods
Method | Description
--- | -----------
authorize | Authorize an amount on the customer's card
complete_authorize | Handle return from off-site gateways after authorization
capture | Capture an amount you have previously authorized
purchase | Authorize and immediately capture an amount on the customer's card
complete_purchase | Handle return from off-site gateways after purchase
refund | Refund an already processed transaction
void | Generally can only be called up to 24 hours after submitting a transaction

#### Paramaters
Key | Type | Description
--- | ---- | -----------
data | Array | An array of data required by the payment gateway
ip*optional* | String | The IP address of the user who is making the payment
return_url*optional* | String | A URL the user will be returned to if the payment is successful
cancel_url*optional* | String | A URL the user will be returned to if they cancel

#### Data array
Key | Type | Description
--- | ---- | -----------
number | Numeric | The credit/debit card number
expiry_month | Numeric | The expiry month of the credit/debit card in two digit format
expiry_year | Numeric | The expiry year of the credit/debit card in four digit format
start_month*optional* | Numeric | The start month of the credit/debit card in two digit format
start_year*optional* | Numeric | The start year of the credit/debit card in four digit format
cvv | Numeric | The three digit CVV code for the credit/debit card
issue_number*optional* | Numeric | The issue number of the credit/debit card
type*optional* | See card types | The credit/debit card type

#### Card types
Name | Slug
---- | ----
Visa | visa
MasterCard | mastercard
Discover | discover
Amex | amex
Diners Club | diners_club
JCB | jcb
Switch | switch
Solo | solo
Dankort | dankort
Maestro | maestro
Forbrugsforeningen | forbrugsforeningen
Laser | laser

<!--code-->
#### Example Successful On-Site Gateway Response
``` json
{
    "status": true,
    "result": {
        "message": "Payment completed successfully",
        "redirect": false,
        "reference": "ch_3zp8J7fHW4lfuP",
        "data": {
            "id": "ch_3zp8J7fHW4lfuP",
            "object": "charge",
            "created": 1399547716,
            "livemode": false,
            "paid": true,
            "amount": 10000,
            "currency": "gbp",
            "refunded": false,
            "card": {
                "id": "card_jksdfj7HBJHBJdkj",
                "object": "card",
                "last4": "4242",
                "type": "Visa",
                "exp_month": 12,
                "exp_year": 2015,
                "fingerprint": "LKJKjbhsdf3343",
                "customer": null,
                "country": "US",
                "name": "Chris Harvey",
                "address_line1": "55 Moltin Lane",
                "address_line2": "",
                "address_city": "Moltinland",
                "address_state": "Moltin",
                "address_zip": "M01T",
                "address_country": "United Kingdom",
                "cvc_check": "pass",
                "address_line1_check": "pass",
                "address_zip_check": "pass"
            },
            "captured": true,
            "balance_transaction": "txn_3hgfsdfGHJGcsdf",
            "failure_message": null,
            "failure_code": null,
            "amount_refunded": 0,
            "customer": null,
            "invoice": null,
            "description": "Order #223",
            "dispute": null,
            "metadata": [],
            "statement_description": null,
            "fee": 260,
            "fee_details": [
                {
                    "amount": 260,
                    "currency": "gbp",
                    "type": "stripe_fee",
                    "description": "Stripe processing fees",
                    "application": null
                }
            ]
        },
        "order": {
            "id": "223",
            "customer": {
                "value": "Chris",
                "data": {
                    "id": "111",
                    "first_name": "Chris",
                    "last_name": "Harvey",
                    "email": "chris@molt.in",
                    "group": null,
                    "created_at": "",
                    "updated_at": ""
                }
            },
            "gateway": {
                "value": "Stripe",
                "data": {
                    "name": "Stripe",
                    "slug": "stripe",
                    "description": null,
                    "enabled": true,
                    "settings": {
                        "apiKey": "That would be telling"
                    }
                }
            },
            "status": {
                "value": "Paid",
                "data": {
                    "key": "paid",
                    "value": "Paid"
                }
            },
            "subtotal": "100.00",
            "shipping_price": "",
            "total": "100.00",
            "currency": {
                "value": "British Pound",
                "data": {
                    "id": 4,
                    "code": "GBP",
                    "title": "British Pound",
                    "enabled": true,
                    "modifier": "+0",
                    "exchange_rate": null,
                    "format": "£{price}",
                    "decimal_point": ".",
                    "thousand_point": ",",
                    "rounding": null,
                    "default": false,
                    "created_at": null,
                    "updated_at": null
                }
            },
            "currency_code": "GBP",
            "exchange_rate": "1.00",
            "ship_to": {
                "value": "",
                "data": {
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
                        "value": "United Kingdom",
                        "data": {
                            "code": "GB",
                            "name": "United Kingdom"
                        }
                    },
                    "customer": {
                        "value": "Chris",
                        "data": {
                            "id": "111",
                            "first_name": "Chris",
                            "last_name": "Harvey",
                            "email": "chris@molt.in",
                            "group": null,
                            "created_at": "",
                            "updated_at": ""
                        }
                    },
                    "company": "",
                    "phone": "123456778",
                    "created_at": "",
                    "updated_at": ""
                }
            },
            "bill_to": {
                "value": "",
                "data": {
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
                        "value": "United Kingdom",
                        "data": {
                            "code": "GB",
                            "name": "United Kingdom"
                        }
                    },
                    "customer": {
                        "value": "Chris",
                        "data": {
                            "id": "111",
                            "first_name": "Chris",
                            "last_name": "Harvey",
                            "email": "chris@molt.in",
                            "group": null,
                            "created_at": "",
                            "updated_at": ""
                        }
                    },
                    "company": "",
                    "phone": "123456778",
                    "created_at": "",
                    "updated_at": ""
                }
            },
            "shipping": null,
            "created_at": "2014-05-08 11:11:44",
            "updated_at": "2014-05-08 11:13:55"
        }
    }
}
```

### Example Failed Response
``` json
{
   "status": false,
   "error": "The number parameter is required"
}
```
<!--/code-->
