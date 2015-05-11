<!--
@title Get collection by ID
@author Moltin Ltd
@description Returns a collection of the given ID

@sidebar 1
@family Collection
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a collection based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}collections/:id]({{ api_url }}collections/:id)

#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": "100",
    "title": "Example Collection",
    "slug": "example-collection",
    "status":
    {
      "key": "1",
      "value": "Live"
    },
    "description": "Example collection description"
  }
}
```


#### Example Empty Response
``` json
{
    "status": false,
    "error": "No collection found"
}
```
<!--/code-->