<!--
@title GET flows
@author Moltin Ltd
@description Gets a list of flows
@order 15.1

@sidebar 1
@family Flow
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns all the flows you have created, including the default flows like products and categories.

#### Resource URL
GET [{{ url }}flows]({{ url }}flows)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of flows to return
offset*optional* | Integer | The first flow to be shown, used for pagination

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": [
        {
            "name": "Categories",
            "slug": "categories",
            "info": "Category data",
            "title_column": "title"
        },
        {
            "name": "Customers",
            "slug": "customers",
            "info": "Customer data",
            "title_column": "first_name"
        },
        {
            "name": "Addresses",
            "slug": "addresses",
            "info": "Customer addresses",
            "title_column": "save_as"
        },
        {
            "name": "Products",
            "slug": "products",
            "info": "Product data",
            "title_column": "tax_band"
        },
        {
            "name": "Orders",
            "slug": "orders",
            "info": "Orders",
            "title_column": null
        },
        {
            "name": "Order Items",
            "slug": "order_items",
            "info": "Order items",
            "title_column": "title"
        },
        {
            "name": "Brands",
            "slug": "brands",
            "info": "Brand data",
            "title_column": "title"
        },
        {
            "name": "Collections",
            "slug": "collections",
            "info": "Collection data",
            "title_column": "title"
        },
        {
            "name": "Shipping",
            "slug": "shipping",
            "info": "Shipping methods",
            "title_column": "title"
        },
        {
            "name": "My awesome custom flow",
            "slug": "my-awesome-custom-flow",
            "info": "Flows are awesome!",
            "title_column": "awesome_field"
        }
    ],
    "pagination": {
        "total": 10,
        "current": 10,
        "limit": 10,
        "offset": 0,
        "from": 1,
        "to": 10,
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