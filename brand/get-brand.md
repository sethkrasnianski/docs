<!--
@title Get single brand by criteria
@author Moltin Ltd
@description Gets a brand based on the given criteria

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a brand based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}brand]({{ url }}brand)


#### parameters
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