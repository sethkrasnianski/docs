<!--
@title GET customer/:id/address
@author Moltin Ltd
@description Gets an address based on the given criteria

@sidebar 1
@family Address
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns an address based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}customer/:id/address]({{ url }}customer/:id/address)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
save_as*optional* | String | The name the address is saved as
company*optional* | String | The name of the company this address belongs to
first_name*optional* | String | First name of the person this address belongs to
last_name*optional* | String | Last name of the person this address belongs to
email*optional* | String | The email address of the person this address belongs to
phone*optional* | String | The telephone number of the person this address belongs to
address_1*optional* | String | Address line 1
address_2*optional* | String | Address line 2
city*optional* | String | Address city
county*optional* | String | Address county
postcode*optional* | String | Address postcode
country*optional* | Enumeration (ISO 3166-1-alpha-2) | Address country

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
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
  }
}
```


### Example Empty Response
``` json
{
    "status": false,
    "error": "No address found"
}
```
<!--/code-->