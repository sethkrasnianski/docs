<!--
@title Get product modifier by ID
@author Moltin Ltd
@description Returns a product modifier of the given ID
@order 3.1.1

@sidebar 1
@family Product/Modifier
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call simply returns a product modifier based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.

#### Resource URL
GET [{{ url }}product/:productId/modifer/:id]({{ url }}product/:productId/modifer/:id)

#### parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "450",
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
        "instructions": "Please select a colour",
        "product": 6,
        "created_at": "2014-05-04 23:41:01",
        "updated_at": "2014-05-06 15:33:10",
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
    "error": "No modifier found"
}
```

#### Usage Example
``` php
try {
    $product = $moltin->get('product/6/modifier/450');
} catch(\Exception $e) {
    exit($e->getMessage());
}
```
<!--/code-->