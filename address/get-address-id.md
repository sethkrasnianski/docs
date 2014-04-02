<!--
@title Get address by ID
@author Moltin Ltd
@description Returns a customers address of the given ID

@sidebar 1
@family Address
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a customers address based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}customer/:id/address/:id]({{ url }}customer/:id/address/:id)


#### Paramaters
None required

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