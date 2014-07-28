<!--
@title Get multiple entries for a flow
@author Moltin Ltd
@description Returns all the entries for a given flow
@order 15.3.2

@sidebar 1
@family Flow/Entry
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This endpoint displays all the entries for a specified slug.

#### Resource URL
GET [{{ url }}flow/:slug/entries]({{ url }}flow/:slug/entries)


#### parameters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of flows to return
offset*optional* | Integer | The first flow to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json


    {
       "status": true,
       "result":
       [
           {
               "id": "100",
               "title": "Hello world",
               "description": ""
           },
           {
               "id": "101",
               "title": "Hello universe",
               "description": "Hello universe, how are you today?"
           }
       ],
       "pagination":
       {
           "total": 4,
           "current": 2,
           "limit": 2,
           "offset": 0,
           "from": 1,
           "to": 2,
           "offsets":
           {
               "first": 0,
               "previous": false,
               "next": 2,
               "last": 2
           },
           "links":
           {
               "first": "https://api.molt.in/beta/flow/my-flow/entries?limit=2",
               "previous": false,
               "next": "https://api.molt.in/beta/flow/my-flow/entries?offset=2&limit=2",
               "last": "https://api.molt.in/beta/flow/my-flow/entries?offset=2&limit=2"
           }
       }
    }


```


#### Example Invalid Slug Response
``` json
{
    "status": false,
    "error": "Flow not found"
}
```
<!--/code-->