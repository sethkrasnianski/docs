<!--
@title GET category/:id
@author Moltin Ltd
@description Returns a category of the given ID
@order 2.3

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a category based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}category/:id]({{ url }}category/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response
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


### Example Empty Response
``` json
{
    "status": false,
    "error": "No category found"
}
```
<!--/code-->