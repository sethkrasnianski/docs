<!--
@title Create new order
@author Moltin Ltd
@description Creates a new order

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new order with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new order will be returned.


#### Resource URL
POST [{{ api_url }}orders]({{ api_url }}orders)


#### Parameters
Key | Type | Description
--- | ---- | -----------
customer*optional* | Integer | Customer ID
gateway*optional* | String | The gateway slug
status | String | The order status, paid, unpaid, dispatched, processing, cancelled, failed, declined, mismatch, refunded, partial_refund
subtotal | Decimal | The order subtotal (before shipping and tax)
shipping_price*optional* | Decimal | Select by shipping price
total | Decimal | The order total (after tax and shipping)
currency | Integer | The currency ID
currency_code | String | The currency code
exchange_rate | Decimal | The currency exchange rate
ship_to | Integer | The customers shipping address
bill_to | Integer | The customers billing address
shipping*optional* | Integer | The shipping method used

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": "150",
    "customer": null,
    "gateway": null,
    "status": {
      "key": "unpaid",
      "value": "Unpaid"
    },
    "subtotal": "100.00",
    "shipping_price": "20.00",
    "total": "120.00",
    "currency": {
      "id": 7,
      "code": "GBP",
      "title": "British Pound",
      "enabled": true,
      "modifier": "*3",
      "exchange_rate": "1.00",
      "format": "£{price}",
      "decimal_point": ".",
      "thousand_point": ",",
      "rounding": "full",
      "default": false
    },
    "currency_code": "GBP",
    "exchange_rate": "1.00",
    "ship_to": {
      "id": "54",
      "save_as": "Home",
      "company": "",
      "first_name": "Cameron",
      "last_name": "Diaz",
      "email": "cameron.diaz@hotmail.com",
      "phone": "22637663429",
      "address_1": "23 Moltin Road",
      "address_2": "",
      "city": "Moltinland",
      "county": "Moltin ",
      "postcode": "M01T 1N",
      "country": {
        "code": "GB",
        "name": "United Kingdom"
      },
      "customer": {
        "id": "53",
        "first_name": "Chris",
        "last_name": "Harvey",
        "email": "chris@molt.in"
      }
    },
    "bill_to": {
      "id": "54",
      "save_as": "Home",
      "company": "",
      "first_name": "Cameron",
      "last_name": "Diaz",
      "email": "cameron.diaz@hotmail.com",
      "phone": "22637663429",
      "address_1": "23 Moltin Road",
      "address_2": "",
      "city": "Moltinland",
      "county": "Moltin ",
      "postcode": "M01T 1N",
      "country": {
        "code": "GB",
        "name": "United Kingdom"
      },
      "customer": {
        "id": "53",
        "first_name": "Chris",
        "last_name": "Harvey",
        "email": "chris@molt.in"
      }
    },
    "shipping": null
  }
}
```


### Example Empty Response
``` json
{
  "status": false,
  "errors": [
    "'99' is not a valid relationship"
  ]
}
```
<!--/code-->