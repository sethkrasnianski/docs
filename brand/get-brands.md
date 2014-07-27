<!--
@title Get multiple brands by criteria
@author Moltin Ltd
@description Gets an array of brands based on the given criteria

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a list of brands based on the given criteria. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ url }}brands]({{ url }}brands)


#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
    {
      "id": "98",
      "title": "Example Brand",
      "slug": "example-brand",
      "status":
      {
        "key": "1",
        "value": "Live"
      },
      "description": "Example brand description"
    }
  ],
  "pagination": {
    "total": 1,
    "current": 1,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 1,
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


### Example Empty Response
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