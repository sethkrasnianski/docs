<!--
@title Update existing collection
@author Moltin Ltd
@description Updates a collection with the given ID

@sidebar 1
@family Collection
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This endpoint edits a collection with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}collection/:id]({{ url }}collection/:id)


#### parameters
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The Title of the collection, must be unique
slug*optional* | String | The Slug/URI of the collection, must be unique
status*optional* | Choice (1 or 0) | Is the collection Live or a Draft
description*optional* | String | The Description of the collection

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