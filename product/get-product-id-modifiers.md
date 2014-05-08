<!--
@title Get product modifiers
@author Moltin Ltd
@description Returns a list of modifiers and variations of the given product
@order 3.5

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of modifiers and variations for a product. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
GET [{{ url }}product/:id/modifiers]({{ url }}product/:id/modifiers)

#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result":
    {
        "450":
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
            "variations":
            {
                "451":
                {
                    "id": "451",
                    "title": "Red",
                    "mod_price": "",
                    "modifier": 450,
                    "product": 0,
                    "created_at": "2014-05-04 23:41:11",
                    "updated_at": "2014-05-05 14:29:05",
                    "difference": "£0.00"
                },
                "496":
                {
                    "id": "496",
                    "title": "Green",
                    "mod_price": "=2.99",
                    "modifier": 450,
                    "product": 0,
                    "created_at": "2014-05-05 20:40:04",
                    "updated_at": "2014-05-05 22:07:42",
                    "difference": "=£2.99"
                },
                "498":
                {
                    "id": "498",
                    "title": "Blue",
                    "mod_price": "+1.50",
                    "modifier": 450,
                    "product": 0,
                    "created_at": "2014-05-05 22:08:33",
                    "updated_at": "2014-05-05 22:08:33",
                    "difference": "+£1.50"
                }
            }
        },
        "457":
        {
            "id": "457",
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
            "instructions": "Please select a size",
            "product": 6,
            "created_at": "2014-05-04 23:41:54",
            "updated_at": "2014-05-06 15:33:23",
            "variations":
            {
                "458":
                {
                    "id": "458",
                    "title": "Small",
                    "mod_price": "-0.50",
                    "modifier": 457,
                    "product": 0,
                    "created_at": "2014-05-04 23:42:06",
                    "updated_at": "2014-05-05 22:10:29",
                    "difference": "-£0.50"
                },
                "500":
                {
                    "id": "500",
                    "title": "Medium",
                    "mod_price": "+0.00",
                    "modifier": 457,
                    "product": 0,
                    "created_at": "2014-05-05 22:09:27",
                    "updated_at": "2014-05-05 22:09:27",
                    "difference": "+£0.00"
                },
                "504":
                {
                    "id": "504",
                    "title": "Large",
                    "mod_price": "+0.50",
                    "modifier": 457,
                    "product": 0,
                    "created_at": "2014-05-05 22:09:41",
                    "updated_at": "2014-05-05 22:09:41",
                    "difference": "+£0.50"
                }
            }
        },
        "478":
        {
            "id": "478",
            "type":
            {
                "value": "Single",
                "data":
                {
                    "key": "single",
                    "value": "Single"
                }
            },
            "title": "Gift Wrap",
            "instructions": "",
            "product": 6,
            "created_at": "2014-05-05 01:05:06",
            "updated_at": "2014-05-05 22:13:41",
            "variations":
            {
                "480":
                {
                    "id": "480",
                    "title": "Yes",
                    "mod_price": "+2.99",
                    "modifier": 478,
                    "product": 0,
                    "created_at": "2014-05-05 01:51:35",
                    "updated_at": "2014-05-05 22:15:20",
                    "difference": "+£2.99"
                },
                "508":
                {
                    "id": "508",
                    "title": "No",
                    "mod_price": "+0.00",
                    "modifier": 478,
                    "product": 0,
                    "created_at": "2014-05-05 22:15:32",
                    "updated_at": "2014-05-05 22:15:32",
                    "difference": "+£0.00"
                }
            }
        },
        "481":
        {
            "id": "481",
            "type":
            {
                "value": "Input",
                "data":
                {
                    "key": "input",
                    "value": "Input"
                }
            },
            "title": "Add a message",
            "instructions": "",
            "product": 6,
            "created_at": "2014-05-05 11:49:19",
            "updated_at": "2014-05-05 11:49:19",
            "variations":
            [
            ]
        },
        "523":
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
            "variations":
            {
                "524":
                {
                    "id": "524",
                    "title": "Red",
                    "mod_price": "-0.50",
                    "modifier": 523,
                    "product": 0,
                    "created_at": "2014-05-07 10:57:58",
                    "updated_at": "2014-05-07 11:03:26",
                    "difference": "-£0.50"
                }
            }
        }
    }
}
```

#### Example Invalid ID Response
``` json
{
    "status": false,
    "error": "No product found"
}
```

#### Usage Example
``` php
try {
    $modifiers = $moltin->get('product/6/modifiers');
} catch(\Exception $e) {
    exit($e->getMessage());
}
```
<!--/code-->