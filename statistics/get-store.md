<!--
@title Get all store metrics for a time period
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
Returns all store metrics in one object. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}statistics/store]({{ url }}statistics/store)


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
        },
        "orders": {
            "total_to_date": 87,
            "frame_total": 11,
            "frame_previous_total": 0,
            "frame_change": 11,
            "frame_change_percent": 0,
            "average_order_value": 100,
            "items": [
                {
                    "order_id": 375,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:47:33"
                },
                {
                    "order_id": 376,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:50:10"
                },
                {
                    "order_id": 377,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:52:56"
                },
                {
                    "order_id": 378,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:53:45"
                },
                {
                    "order_id": 379,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:53:58"
                },
                {
                    "order_id": 380,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:54:00"
                },
                {
                    "order_id": 381,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:54:21"
                },
                {
                    "order_id": 382,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:55:40"
                },
                {
                    "order_id": 383,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 21:56:06"
                },
                {
                    "order_id": 385,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-19 22:10:43"
                },
                {
                    "order_id": 386,
                    "status": "unpaid",
                    "total": "100.00",
                    "created_at": "2014-07-22 14:27:46"
                }
            ]
        },
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
                    "data": "\"email\"=>\"test@molt.in\", \"group\"=>\"372\", \"last_name\"=>\"Smith\", \"first_name\"=>\"John\"",
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