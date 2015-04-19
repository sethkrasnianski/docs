<!--
@title Get customer by ID
@author Moltin Ltd
@description Returns a customer of the given ID

@sidebar 1
@family Customer
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a customer based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}customer/:id]({{ api_url }}customer/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response   
``` json
{
  "status": true,
  "result": {
    "id": "53",
    "first_name": "Chris",
    "last_name": "Harvey",
    "email": "chris@molt.in",
    "history": {
      "orders": 98,
      "value": "3,003.00"
    }
  }
}
```


#### Example Empty Response 
``` json
{
    "status": false,
    "error": "No customer found"
}
```
<!--/code-->