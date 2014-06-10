<!--
@title Get order items by criteria
@author Moltin Ltd
@description Gets an array of items for a specified order

@sidebar 1
@family Order/Order Item
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns an array of order items for a specified order.


#### Resource URL
GET [{{ url }}order/:id/items]({{ url }}order/:id/items)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of order items to return, defaults to all
offset*optional* | Integer | The first order item to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
   "status": true,
   "result":
   [
       {
           "id": "994",
           "product":
           {
               "value": "Espresso Cup - Small Red",
               "data":
               {
                   "id": "949",
                   "sku": "PRD_H0003_SMRE",
                   "title": "Espresso Cup - Small Red",
                   "slug": "espresso-cup-small-red",
                   "price": "14.99",
                   "sale_price": "12.99",
                   "status":
                   {
                       "value": "Live",
                       "data":
                       {
                           "key": "1",
                           "value": "Live"
                       }
                   },
                   "category":
                   {
                       "value": "Featured",
                       "data":
                       {
                           "60":
                           {
                               "id": "60",
                               "parent": null,
                               "title": "Featured",
                               "slug": "featured",
                               "status":
                               {
                                   "value": "Live",
                                   "data":
                                   {
                                       "key": "1",
                                       "value": "Live"
                                   }
                               },
                               "description": "Featured products",
                               "created_at": "",
                               "updated_at": ""
                           }
                       }
                   },
                   "stock_level": 1034,
                   "stock_status":
                   {
                       "value": "In Stock",
                       "data":
                       {
                           "key": "1",
                           "value": "In Stock"
                       }
                   },
                   "description": "Start the day off right with a shot of your favourite coffee from one of these gorgeous little cups!",
                   "requires_shipping":
                   {
                       "value": "Yes",
                       "data":
                       {
                           "key": "1",
                           "value": "Yes"
                       }
                   },
                   "weight": "10.00",
                   "height": "10.00",
                   "width": "10.00",
                   "depth": "10.00",
                   "collection": null,
                   "brand": null,
                   "tax_band":
                   {
                       "value": "Default",
                       "data":
                       {
                           "id": 1,
                           "title": "Default",
                           "description": null,
                           "rate": "20.00",
                           "created_at": null,
                           "updated_at": null
                       }
                   },
                   "meta_title": "",
                   "created_at": "2014-05-19 10:46:27",
                   "updated_at": "2014-05-19 10:46:28"
               }
           },
           "sku": "PRD_H0003_SMRE",
           "title": "Espresso Cup - Small Red",
           "price": "14.99",
           "quantity": 1,
           "tax_rate": "20.00",
           "tax_band":
           {
               "value": "Default",
               "data":
               {
                   "id": 1,
                   "title": "Default",
                   "description": null,
                   "rate": "20.00",
                   "created_at": null,
                   "updated_at": null
               }
           },
           "created_at": "2014-05-30 12:44:41",
           "updated_at": "2014-05-30 12:44:41"
       },
       [..]
   ],
   "pagination":
   {
       "total": 10,
       "current": 10,
       "limit": 10,
       "offset": 0,
       "from": 1,
       "to": 10,
       "offsets":
       {
           "first": false,
           "previous": false,
           "next": false,
           "last": false
       },
       "links":
       {
           "first": false,
           "previous": false,
           "next": false,
           "last": false
       }
   }
}
```


### Example Empty Response
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