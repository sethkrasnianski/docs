<!--
@title Get product variation by ID
@author Moltin Ltd
@description Returns a product variation of the given ID
@order 3.1.1.1

@sidebar 1
@family Product/Modifier/Variation
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call simply returns a product variation based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.

#### Resource URL
GET [{{ url }}product/:productId/modifer/:modifierId/variation/:id]({{ url }}product/:productId/modifer/:modifierId/variation/:id)

#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "id": "524",
        "title": "Red",
        "mod_price": "-0.50",
        "modifier": 523,
        "product": 0,
        "created_at": "2014-05-07 10:57:58",
        "updated_at": "2014-05-07 11:03:26"
    }
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "No variation found"
}
```

#### Usage Example
``` php
try {
    $variation = $moltin->get('product/6/modifier/450/variation/524');
} catch(\Exception $e) {
    exit($e->getMessage());
}
```
<!--/code-->