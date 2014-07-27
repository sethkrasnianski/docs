<!--
@title Update a product modifier
@author Moltin Ltd
@description Updates a product modifier with the given ID
@order 3.1.6

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a product modifier with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.

#### Resource URL
PUT [{{ url }}product/:productId/modifier/:id]({{ url }}product/:productId/modifier/:id)

#### parameters
Key | Type | Description
--- | ---- | -----------
title | String | The Title of the modifier, must be unique per product
type | Choice | variant, single or input
instructions*optional* | Text | Any associated instructions for this modifier

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "523",
        "type":
        {
            "value": "Variant",
            "data":
            {
                "key": "variant",
                "value": "Variant"
            }
        },
        "title": "Colour",
        "instructions": "Updated instructions",
        "product": 6,
        "created_at": "2014-05-07 10:29:34",
        "updated_at": "2014-05-07 10:40:53",
        "images":
        [
        ]
    }
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "errors": [
    	"Title must be unique"
    ]
}
```
<!--/code-->