<!--
@title Get customer metrics by timeframe
@author Moltin Ltd
@description Gets some helpful statistical data for store customers based on a time frame

@sidebar 1
@family Statistics
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a set of customer statistics for the store. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}statistics/customers]({{ url }}statistics/customers)


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
        "customers": {
            "total_to_date": 3,
            "frame_total": 1,
            "frame_previous_total": 0,
            "frame_change": 1,
            "frame_change_percent": 0,
            "items": [
                {
                    "id": 373,
                    "flow_id": 57,
                    "store_id": 1,
                    "data": "\"email\"=>\"chris@molt.in2\", \"group\"=>\"372\", \"last_name\"=>\"Harvey\", \"first_name\"=>\"Chris\"",
                    "order": null,
                    "created_at": "2014-07-09 10:50:45",
                    "updated_at": "2014-07-09 10:50:45"
                }
            ]
        }
    }
}
```
<!--/code-->