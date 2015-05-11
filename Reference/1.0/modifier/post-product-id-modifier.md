<!--
@title Create new product modifier
@author Moltin Ltd
@description Creates a new product modifier
@order 3.1.5

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http POST
@version beta
-->
This call creates a new product modifier with the POST data provided. If there are any problems with the creation these will be returned in an errors array listing all validation problems, otherwise the new modifier will be returned.

#### Resource URL
POST [{{ api_url }}products/:productId/modifiers]({{ api_url }}products/:productId/modifiers)

#### Parameters
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
        "title": "Size",
        "instructions": "Example size modifier",
        "product": 6,
        "created_at": "2014-05-07 10:29:34",
        "updated_at": "2014-05-07 10:29:34",
        "images":
        [
        ]
    }
}
```

#### Example Invalid Title Response
``` json
{
    "status": false,
    "errors":
    [
        "The title must be unique for the product"
    ]
}
```
<!--/code-->