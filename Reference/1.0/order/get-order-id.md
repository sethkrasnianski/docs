<!--
@title Get order by ID
@author Moltin Ltd
@description Returns an order of the given ID

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns an order based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}order/:id]({{ api_url }}order/:id)


#### Parameters
None required

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
      "postcode": "M01T 1 N",
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
    "error": "No order found"
}
```
<!--/code-->