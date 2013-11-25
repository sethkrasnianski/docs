<!--
@title GET orders
@author Moltin Ltd
@description Gets an array of orders

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of orders based on a given set of paramaters. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ url }}orders]({{ url }}orders)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of orders to return, defaults to all
offset*optional* | Integer | The first order to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
    {
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
  ],
  "pagination": {
    "total": 1,
    "current": 1,
    "limit": 10,
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


### Example Empty Response
``` json
{
  "status": true,
  "result": [],
  "pagination": {
    "total": 0,
    "current": 0,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 0,
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