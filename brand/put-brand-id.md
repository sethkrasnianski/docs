<!--
@title Update a brand
@author Moltin Ltd
@description Updates a brand with the given ID

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint edits a brand with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}brand/:id]({{ url }}brand/:id)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The Title of the brand, must be unique
slug*optional* | String | The Slug/URI of the brand, must be unique
status*optional* | Choice (1 or 0) | Is the brand Live or a Draft
description*optional* | String | The Description of the brand

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


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "Slug must be unqiue"
  ]
}
```
<!--/code-->