<!--
@title Get single customer by criteria
@author Moltin Ltd
@description Gets a customer based on the given criteria

@sidebar 1
@family Customer
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a customer based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}customer]({{ url }}customer)


#### parameters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
first_name*optional* | String | Select by first name
last_name*optional* | String | Select by last name
email*optional* | String | Select by email

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": "63",
    "first_name": "Adam",
    "last_name": "Sturrock",
    "email": "adam@molt.in",
    "history": {
      "orders": 94,
      "value": "264.00"
    }
  }
}
```


### Example Empty Response
``` json
{
    "status": false,
    "error": "No customer found"
}
```
<!--/code-->