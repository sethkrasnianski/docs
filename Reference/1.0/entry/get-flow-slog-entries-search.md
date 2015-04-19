This call returns a range of entries based on the provided search criteria. Using limit and offset you can also paginate the results. The search parameters available will depend on the fields that you have added to this flow.

#### Resource URL
GET [{{ api_url }}flow/:slug/entries/search]({{ api_url }}flow/:slug/entries/search)


#### Parameters
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