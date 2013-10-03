<!--
@title PUT category/:id
@author Moltin Ltd
@description Updates a category with the given ID

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a category with a given ID. There are no minumum required paramaters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL	{#resource}
POST [{{ url }}cateogry/:id]({{ url }}cateogry/:id)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The Title of the category, must be unique
slug*optional* | String | The Slug/URI of the category, must be unique
parent*optional* | Integer | The Parent category ID of the category, can be null
status*optional* | Choice (1 or 0) | Is the product Live or a Draft
description*optional* | String | The Description of the product


#### Example Successful Response	{#success}
``` json
TBA
```


### Example Empty Response	{#error}
``` json
{
    "status": false,
    "errors": [
        "Slug must be unique",
        "Description is required"
    ]
}
```