<!--
@title POST category
@author Moltin Ltd
@description Creates a new category

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new category with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new category will be returned.


#### Resource URL	{#resource}
POST [{{ url }}cateogry]({{ url }}cateogry)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
title | String | The Title of the category, must be unique
slug | String | The Slug/URI of the category, must be unique
parent | Integer | The Parent category ID of the category, can be null
status | Choice (1 or 0) | Is the product Live or a Draft
description | String | The Description of the product

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