<!--
@title Get item from cart by identifier
@author Moltin Ltd
@description Gets an item from the cart with a given identifier
@order 4.4

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->


You can retrieve a specific item from the cart by calling this endpoint with the cart identifier and item identifier.


#### Resource URL
GET [{{ api_url }}cart/:identifier/item/:id]({{ api_url }}cart/:identifier/item/:id])


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "item": {
    "id": "14",
    "quantity": "1",
    "sku": "PRD_H0001",
    "title": "Choc Fondue Pot",
    "slug": "choc-fondue-pot",
    "price": "17.99",
    "sale_price": "14.99",
    "status": {
      "key": "1",
      "value": "Live"
    },
    "category": {
      "id": "60",
      "parent": null,
      "title": "Featured",
      "slug": "featured",
      "status": {
        "key": "1",
        "value": "Live"
      },
      "description": "Featured products"
    },
    "stock_level": 8892,
    "stock_status": {
      "key": "1",
      "value": "In Stock"
    },
    "description": "Make your favorite sweets extra special with a coating of freshly melted Chocolate! This chocolate Fondue set makes dessert a fun shared experience, perfect for a romantic meal or for celebrations with friends and family. Always a great gift idea for the chocoholic in your life!",
    "requires_shipping": {
      "key": "1",
      "value": "Yes"
    },
    "weight": "234.00",
    "height": "24.00",
    "width": "24.00",
    "depth": "32.00",
    "tax_band": {
      "id": 1,
      "title": "Default",
      "description": null,
      "rate": "20.00"
    },
    "pricing": {
      "formatted": {
        "with_tax": "£22.00",
        "without_tax": "£18.33"
        "tax": "£3.67"
      },
      "rounded": {
        "with_tax": 22,
        "without_tax": 18.33
        "tax": 3.67
      },
      "raw": {
        "with_tax": 21.588,
        "without_tax": 17.99
        "tax": 3.598
      }
    },
    "images": {
      "60": {
        "id": 60,
        "name": "fonduepot1.jpg",
        "url": {
          "http": "http://d2xufakadxl3ok.cloudfront.net/1/fonduepot1.jpg",
          "https": "https://d2xufakadxl3ok.cloudfront.net/1/fonduepot1.jpg"
        }
      },
      "61": {
        "id": 61,
        "name": "fonduepot2.jpg",
        "url": {
          "http": "http://d2xufakadxl3ok.cloudfront.net/1/fonduepot2.jpg",
          "https": "https://d2xufakadxl3ok.cloudfront.net/1/fonduepot2.jpg"
        }
      },
      "62": {
        "id": 62,
        "name": "fonduepot3.jpg",
        "url": {
          "http": "http://d2xufakadxl3ok.cloudfront.net/1/fonduepot3.jpg",
          "https": "https://d2xufakadxl3ok.cloudfront.net/1/fonduepot3.jpg"
        }
      }
    },
    "name": "Choc Fondue Pot",
    "tax": "20.00",
    "total": 21.588,
    "total_before_tax": 17.99,
    "totals": {
      "formatted": {
        "with_tax": "£22.00",
        "without_tax": "£18.33"
        "tax": "£3.67"
      },
      "rounded": {
        "with_tax": 22,
        "without_tax": 18.33
        "tax": 3.67
      },
      "raw": {
        "with_tax": 21.588,
        "without_tax": 17.99
        "tax": 3.598
      }
    }
  }
}
```

#### Example Failed Response
``` json
{
  "status": false,
  "error": "Item does not exist"
}
```
<!--/code-->