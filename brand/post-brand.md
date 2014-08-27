<!--
@title Create new brand
@author Moltin Ltd
@description Creates a new brand

@sidebar 1
@family Brand
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

This endpoint creates a new brand with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new brand will be returned.


#### Resource URL
POST [{{ url }}brand]({{ url }}brand)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title | String | The Title of the brand, must be unique
slug | String | The Slug/URI of the brand, must be unique
status | Choice (1 or 0) | Is the brand Live or a Draft
description | String | The Description of the brand

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
    "Title is required",
    "Slug must be unique"
  ]
}
```
<!--/code-->