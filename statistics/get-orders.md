<!--
@title Get some revenue breakdowns for a time period
@author Moltin Ltd
@description Gets a customer based on the given criteria

@sidebar 1
@family Statistics
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a set of revenue statistics for the store. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}statistics/revenue]({{ url }}statistics/revenue)


#### Parameters
Key | Type | Description
--- | ---- | -----------
timeframe*optional* | Choice | (24hours, 7days, 30days)
from*optional* | Datetime | (YYYY-MM-DD HH:MM:SS) Set the date to start from 
to*optional* | Datetime | (YYYY-MM-DD HH:MM:SS) Set the date to end at 

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
<!--/code-->