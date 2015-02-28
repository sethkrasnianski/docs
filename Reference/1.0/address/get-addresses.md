Returns a list of addresses for a particular customer. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ api_url }}customer/:id/addresses]({{ api_url }}customer/:id/addresses)


#### Parameters
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
  "result": [
    {
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