This endpoint creates a new address for a customer with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new address will be returned.


#### Resource URL
POST [{{ api_url }}customer/:id/address]({{ api_url }}customer/:id/address)


#### Parameters
Key | Type | Description
--- | ---- | -----------
save_as*optional* | String | The name the address is saved as
company*optional* | String | The name of the company this address belongs to
first_name | String | First name of the person this address belongs to
last_name | String | Last name of the person this address belongs to
phone | String | The telephone number of the person this address belongs to
address_1 | String | Address line 1
address_2*optional* | String | Address line 2
city | String | Address city
county | String | Address county
postcode | String | Address postcode
country | Enumeration (ISO 3166-1-alpha-2) | Address country

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
    "phone": "1234567890",
    "address_1": "24 Moltin Road",
    "address_2": "",
    "city": "Moltinland",
    "county": "Moltin",
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


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "First Name is required",
    "Last Name is required",
    "Email Address is required",
    "Phone is required",
    "Address Line 1 is required",
    "City is required",
    "County is required",
    "Postcode is required",
    "Country is required"
  ]
}
```
<!--/code-->