<!--
@title Get brand by ID
@author Moltin Ltd
@description Returns a brand of the given ID

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a brand based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}brand/:id]({{ url }}brand/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
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
}
```


### Example Empty Response
``` json
{
    "status": false,
    "error": "No brand found"
}
```
<!--/code-->