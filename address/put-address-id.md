<!--
@title PUT customer/:id/address/:id
@author Moltin Ltd
@description Updates a customers address with the given ID

@sidebar 1
@family Address
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint edits a customers address with a given ID. There are no minumum required paramaters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}customer/:id/address/:id]({{ url }}customer/:id/address/:id)


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
    "id": "55",
    "save_as": "Home",
    "company": "",
    "first_name": "John",
    "last_name": "Moltin",
    "email": "john@molt.in",
    "phone": "1234567890",
    "address_1": "24 Moltin Road",
    "address_2": "",
    "city": "Moltinland",
    "county": "Moltin",
    "postcode": "M01T 1N",
    "country": {
      "code": "US",
      "name": "United States"
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


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "'MOLTIN' is not a valid country"
  ]
}
```
<!--/code-->