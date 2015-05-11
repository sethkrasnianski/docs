<!--
@title Create new collection
@author Moltin Ltd
@description Creates a new collection

@sidebar 1
@family Collection
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->

This endpoint creates a new collection with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new collection will be returned.


#### Resource URL
POST [{{ api_url }}collections]({{ api_url }}collections)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title | String | The Title of the collection, must be unique
slug | String | The Slug/URI of the collection, must be unique
status | Choice (1 or 0) | Is the collection Live or a Draft
description | String | The Description of the collection

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


#### Example Failed Response
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