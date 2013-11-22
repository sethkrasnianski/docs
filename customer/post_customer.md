<!--
@title POST customer
@author Moltin Ltd
@description Creates a new customer

@sidebar 1
@family Customer
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This endpoint creates a new customer with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new customer will be returned.


#### Resource URL	{#resource}
POST [{{ url }}customer]({{ url }}customer)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
first_name | String | The customer's first name
last_name | String | The customer's last name
email | String | The customer's email

<!--code-->
#### Example Successful Response	{#success}
``` json
{
  "status": true,
  "result": {
    "id": "142",
    "first_name": "John",
    "last_name": "Moltin",
    "email": "john@molt.in",
    "history": {
      "orders": 0,
      "value": 0
    }
  }
}
```


### Example Failed Response	{#error}
``` json
{
  "status": false,
  "errors": [
    "Last Name is required",
    "Email Address is required"
  ]
}
```
<!--/code-->