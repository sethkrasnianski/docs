<!--
@title Get multiple customers by criteria
@author Moltin Ltd
@description Gets an array of customers

@sidebar 1
@family Customer
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a range of customers based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL  
GET [{{ api_url }}customers]({{ api_url }}customers)


#### Parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of customers to return, defaults to all
offset*optional* | Integer | The first customer to be shown, used for pagination

<!--code-->
#### Example Successful Response   
``` json
{
  "status": true,
  "result": [
    {
      "id": "63",
      "first_name": "Adam",
      "last_name": "Sturrock",
      "email": "adam@molt.in",
      "history": {
        "orders": 22,
        "value": "609.00"
      }
    },
    {
      "id": "53",
      "first_name": "Chris",
      "last_name": "Harvey",
      "email": "chris@molt.in",
      "history": {
        "orders": 85,
        "value": "1,480.00"
      }
    },
    {
      "id": "65",
      "first_name": "Jamie",
      "last_name": "Holdroyd",
      "email": "jamie@molt.in",
      "history": {
        "orders": 48,
        "value": "1,601.00"
      }
    }
  ],
  "pagination": {
    "total": 3,
    "current": 3,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 3,
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


#### Example Empty Response 
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