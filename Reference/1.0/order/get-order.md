<!--
@title Get single order by criteria
@author Moltin Ltd
@description Gets an order based on the given criteria

@sidebar 1
@family Order
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns an order based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}order]({{ api_url }}order)


#### Parameters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
customer*optional* | Integer | Select by customer ID
gateway*optional* | String | Select by gateway slug
status*optional* | String | Select by Status Key, 1 or 0
subtotal*optional* | Decimal | Select by subtotal
shipping_price*optional* | Decimal | Select by shipping price
total*optional* | Decimal | Select by the order total
currency*optional* | Integer | Select by currency id
currency_code*optional* | String | Select by currency code
exchange_rate*optional* | Decimal | Select by exchange rate
ship_to*optional* | Integer | Select by shipping address
bill_to*optional* | Integer | Select by billing address
shipping*optional* | Integer | Select by shipping method ID

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
  "status": true,
  "result": []
}
```
<!--/code-->