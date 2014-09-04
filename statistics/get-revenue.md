<!--
@title Get revenue metrics by timeframe
@author Moltin Ltd
@description Gets some helpful statistical data for store revenue based on a time frame

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
        "revenue": {
            "total_to_date": "8700.00",
            "frame_total": "1100.00",
            "frame_previous_total": 0,
            "frame_change": 1100,
            "frame_change_percent": 0
        }
    }
}
```
<!--/code-->