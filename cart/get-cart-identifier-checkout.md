<!--
@title Get the available checkout options
@author Moltin Ltd
@description Retrieve available checkout options for a cart
@order 4.8

@sidebar 1
@family Cart
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

When you are ready to take a cart to checkout, you can make a call to the checkout endpoint to see what shipping methods, addresses and payment gateways are available for the contents of the specified cart.


#### Resource URL
GET [{{ url }}cart/:identifier/checkout]({{ url }}cart/:identifier/checkout])


#### Parameters
Key | Type | Description
--- | ---- | -----------
customer*optional* | Integer or String | The ID or email address of the customer who is checking out

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "cart": {
      "contents": {
        "027c91341fd5cf4d2579b49c4b6a90da": {
          "id": "1",
          "title": "My awesome product",
          "quantity": "1",
          "sku": "AWESOME",
          "slug": "my-awesome-product",
          "price": "35.00",
          "sale_price": "30.00",
          "status": {
            "key": "1",
            "value": "Live"
          },
          "category": null,
          "stock_level": 100,
          "stock_status": {
            "key": "1",
            "value": "In Stock"
          },
          "description": "An awesome product.",
          "requires_shipping": {
            "key": "1",
            "value": "Yes"
          },
          "weight": "10.00",
          "height": "10.00",
          "width": "10.00",
          "depth": "10.00",
          "collection": null,
          "brand": null,
          "tax_band": null,
          "pricing": {
            "formatted": {
              "with_tax": "£35.00",
              "without_tax": "£35.00"
              "tax": "£0.00"
            },
            "rounded": {
              "with_tax": 35,
              "without_tax": 35,
              "tax": 0
            },
            "raw": {
              "with_tax": 35,
              "without_tax": 35,
              "tax": 0
            }
          },
          "images": [],
          "name": "My awesome product",
          "total": 35,
          "total_before_tax": 35,
          "totals": {
            "formatted": {
              "with_tax": "£35.00",
              "without_tax": "£35.00",
              "tax": "£0.00"
            },
            "rounded": {
              "with_tax": 35,
              "without_tax": 35,
              "tax": 0
            },
            "raw": {
              "with_tax": 35,
              "without_tax": 35,
              "tax": 0
            }
          }
        }
      },
      "totals": {
        "formatted": {
          "with_tax": "£35.00",
          "without_tax": "£35.00",
          "tax": "£0.00"
        },
        "rounded": {
          "with_tax": 35,
          "without_tax": 35,
          "tax": 0
        },
        "raw": {
          "with_tax": 35,
          "without_tax": 35,
          "tax": 0
        }
      }
    },
    "shipping": {
      "required": true,
      "methods": [
        {
          "id": "70",
          "title": "£5 Shipping",
          "slug": "5-shipping",
          "company": "FedEx",
          "status": {
            "key": "1",
            "value": "Live"
          },
          "price": "5.00",
          "price_min": "",
          "price_max": "",
          "weight_min": "",
          "weight_max": "",
          "description": "",
          "tax_band": {
            "id": 1,
            "title": "Default",
            "description": null,
            "rate": "20.00"
          },
          "pricing": {
            "formatted": {
              "with_tax": "£6.00",
              "without_tax": "£5.00"
            },
            "rounded": {
              "with_tax": 6,
              "without_tax": 5
            },
            "raw": {
              "with_tax": 6,
              "without_tax": 5
            }
          },
          "totals": {
            "formatted": {
              "with_tax": "£41.00",
              "without_tax": "£40.00"
            },
            "rounded": {
              "with_tax": 41,
              "without_tax": 40
            },
            "raw": {
              "with_tax": 41,
              "without_tax": 40
            }
          }
        }
      ]
    },
    "addresses": [],
    "gateways": {
      "paypal-express": {
        "id": 4,
        "store_id": 1,
        "name": "PayPal Express",
        "slug": "paypal-express",
        "description": null,
        "enabled": true,
        "settings": {
          "username": "my-paypal-username",
          "password": "password",
          "signature": "signaturehere",
          "testMode": true,
          "solutionType": "Sole",
          "landingPage": "Billing",
          "headerImageUrl": ""
        }
      },
      "2checkout": {
        "id": 6,
        "store_id": 1,
        "name": "2Checkout",
        "slug": "2checkout",
        "description": null,
        "enabled": true,
        "settings": {
          "accountNumber": "my-account-no",
          "secretWord": "this-is-a-secret",
          "testMode": false
        }
      }
    }
  }
}
```
<!--/code-->