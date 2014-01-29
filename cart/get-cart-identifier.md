<!--
@title GET cart/:identifier
@author Moltin Ltd
@description Retrieve the cart contents
@order 4.3

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

You can retrieve the shopping cart by calling the cart endpoint and pass the cart identifier as part of the URL.


#### Resource URL
GET [{{ url }}cart/:identifier]({{ url }}cart/:identifier])


#### Paramaters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "contents": {
    "bb4a6db4295d6be8bd12791ed5650087": {
      "id": "14",
      "quantity": 2,
      "/beta/cart/123": "",
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
        },
        "rounded": {
          "with_tax": 22,
          "without_tax": 18.33
        },
        "raw": {
          "with_tax": 21.588,
          "without_tax": 17.99
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
      "total": 43.176,
      "total_before_tax": 35.98,
      "totals": {
        "formatted": {
          "with_tax": "£44.00",
          "without_tax": "£36.66"
        },
        "rounded": {
          "with_tax": 44,
          "without_tax": 36.66
        },
        "raw": {
          "with_tax": 43.176,
          "without_tax": 35.98
        }
      }
    }
  },
  "total": 43.176,
  "total_before_tax": 35.98,
  "total_items": 2,
  "total_unique_items": 2,
  "totals": {
    "formatted": {
      "with_tax": "£44.00",
      "without_tax": "£36.66"
    },
    "rounded": {
      "with_tax": 44,
      "without_tax": 36.66
    },
    "raw": {
      "with_tax": 43.176,
      "without_tax": 35.98
    }
  },
  "currency": {
    "code": "GBP",
    "format": "£{price}",
    "decimal": ".",
    "thousand": ",",
    "rounding": "full"
  }
}
```
<!--/code-->