<!--
@title GET category
@author Moltin Ltd
@description Gets a category based on the given criteria

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a category based on a given set of key-value properties. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL	{#resource}
[{{ url }}category]({{ url }}category)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
title*optional* | String | Select by Title
slug*optional* | String | Select by Slug
parent*optional* | Integer | Select by Parent ID
status*optional* | Integer | Select by Status Key, 1 or 0

<!--code-->
#### Example Successful Response	{#success}
``` json
{
    "status": true,
    "result": {
        "id": 18,
        "parent": {
            "id": 17,
            "parent": null,
            "title": "Test Category 7",
            "slug": "test-category-7",
            "status": {
                "key": "1",
                "value": "Live"
            },
            "description": "Description"
        },
        "title": "Test Category 3",
        "slug": "test-category-3",
        "status": {
            "key": "1",
            "value": "Live"
        },
        "description": "Desc",
        "images": [

        ]
    }
}
```


### Example Empty Response	{#error}
``` json
{
    "status": false,
    "error": "No category found"
}
```
<!--/code-->