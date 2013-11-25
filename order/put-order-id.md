<!--
@title PUT order/:id
@author Moltin Ltd
@description Updates an order with the given ID

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits an order with a given ID. There are no minumum required paramaters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}order/:id]({{ url }}order/:id)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
customer*optional* | Integer | Customer ID
gateway*optional* | String | The gateway slug
status*optional* | String | The order status, 1 or 0
subtotal*optional* | Decimal | The order subtotal (before shipping and tax)
shipping_price*optional* | Decimal | Select by shipping price
total*optional* | Decimal | The order total (after tax and shipping)
currency*optional* | Integer | The currency ID
currency_code*optional* | String | The currency code
exchange_rate*optional* | Decimal | The currency exchange rate
ship_to*optional* | Integer | The customers shipping address
bill_to*optional* | Integer | The customers billing address
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
    "shipping_price": "30.00",
    "total": "130.00",
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


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "Invalid decimal value for Subtotal"
  ]
}
```
<!--/code-->