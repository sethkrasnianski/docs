<!--
@title Get single collection by criteria
@author Moltin Ltd
@description Gets a collection based on the given criteria

@sidebar 1
@family Collection
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a collection based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}collection]({{ url }}collection)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
title*optional* | String | Select by Title
slug*optional* | String | Select by Slug
status*optional* | Choice (1 or 0) | Select by Status

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


### Example Empty Response
``` json
{
    "status": false,
    "error": "No collection found"
}
```
<!--/code-->