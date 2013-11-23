<!--
@title GET categories
@author Moltin Ltd
@description Gets an array of categories

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of categories based on a given set of paramaters. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL	{#resource}
GET [{{ url }}categories]({{ url }}categories)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of categories to return, defaults to all
offset*optional* | Integer | The first category to be shown, used for pagination

<!--code-->
#### Example Successful Response	{#success}
``` json
{
  "status": true,
  "result": [
    {
      "id": "60",
      "parent": null,
      "title": "Featured",
      "slug": "featured",
      "status": {
        "key": "1",
        "value": "Live"
      },
      "description": "Featured products",
      "images": []
    },
    {
      "id": "16",
      "parent": null,
      "title": "Accessories",
      "slug": "accessories",
      "status": {
        "key": "1",
        "value": "Live"
      },
      "description": "Shop for all your must have accessories!",
      "images": []
    },
    {
      "id": "42",
      "parent": null,
      "title": "Arts and Crafts",
      "slug": "arts-and-crafts",
      "status": {
        "key": "1",
        "value": "Live"
      },
      "description": "Good quality art materials at affordable prices. We're here to help you create without limits!",
      "images": []
    },
    {
      "id": "17",
      "parent": null,
      "title": "Household",
      "slug": "household",
      "status": {
        "key": "1",
        "value": "Live"
      },
      "description": "Household items and decorative ornaments.",
      "images": []
    }
  ],
  "pagination": {
    "total": 4,
    "current": 4,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 4,
    "offsets": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    },
    "links": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    }
  }
}
```


### Example Empty Response	{#error}
``` json
{
  "status": true,
  "result": [],
  "pagination": {
    "total": 0,
    "current": 0,
    "limit": 10,
    "offset": 0,
    "from": 1,
    "to": 0,
    "offsets": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    },
    "links": {
      "first": false,
      "previous": false,
      "next": false,
      "last": false
    }
  }
}
```
<!--/code-->