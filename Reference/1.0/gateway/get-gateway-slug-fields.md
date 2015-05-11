This call returns the data required to build a dynamic flows form based on the gateway edit requirements. It provides all options available for the choice fields as well as those featured in relationships. It also provides information of field requirements, default values, etc.

Unlike /gateways/fields this adds the current gateways data to the array to allow for prepopulation of fields.

#### Resource URL
[{{ api_url }}gateways/:id/fields]({{ api_url }}gateways/:id/fields)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "sku": {
      "slug": "sku",
      "name": "SKU",
      "type": "string",
      "options": [],
      "required": true,
      "unique": true,
      "locked": true,
      "order": 1,
      "value": "PRD_H0001"
    },
    "title": {
      "slug": "title",
      "name": "Product Title",
      "type": "string",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 2,
      "value": "Choc Fondue Pot"
    },
    "slug": {
      "slug": "slug",
      "name": "Slug",
      "type": "slug",
      "options": {
        "parent": "title"
      },
      "required": true,
      "unique": true,
      "locked": true,
      "order": 3,
      "value": "choc-fondue-pot"
    },
    "price": {
      "slug": "price",
      "name": "Price",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": true,
      "unique": false,
      "locked": true,
      "order": 4,
      "value": "17.99"
    },
    "sale_price": {
      "slug": "sale_price",
      "name": "Sale Price",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": false,
      "unique": false,
      "locked": false,
      "order": 5,
      "value": "14.99"
    },
    "status": {
      "slug": "status",
      "name": "Status",
      "type": "choice",
      "options": {
        "choices": [
          "Draft",
          "Live"
        ],
        "default": 0
      },
      "required": true,
      "unique": false,
      "locked": true,
      "order": 6,
      "value": {
        "key": "1",
        "value": "Live"
      }
    },
    "category": {
      "slug": "category",
      "name": "Category",
      "type": "relationship",
      "options": {},
      "required": true,
      "unique": false,
      "locked": true,
      "order": 7,
      "available": {
        "16": "Accessories",
        "17": "Household",
        "42": "Arts and Crafts",
        "60": "I have just updated my title, isn't that great!",
        "137": "My Awesome New Category"
      },
      "value": {
        "id": "60",
        "parent": null,
        "title": "I have just updated my title, isn't that great!",
        "slug": "featured",
        "status": {
          "key": "1",
          "value": "Live"
        },
        "description": "Featured products"
      }
    },
    "stock_level": {
      "slug": "stock_level",
      "name": "Stock Level",
      "type": "integer",
      "options": {
        "default": false
      },
      "required": true,
      "unique": false,
      "locked": true,
      "order": 8,
      "value": 8892
    },
    "stock_status": {
      "slug": "stock_status",
      "name": "Stock Status",
      "type": "choice",
      "options": {
        "choices": [
          "Unlimited",
          "In Stock",
          "Low Stock",
          "Out Of Stock",
          "More Stock Ordered",
          "Discontinued"
        ],
        "default": 1
      },
      "required": true,
      "unique": false,
      "locked": true,
      "order": 9,
      "value": {
        "key": "1",
        "value": "In Stock"
      }
    },
    "description": {
      "slug": "description",
      "name": "Description",
      "type": "text",
      "options": [],
      "required": true,
      "unique": false,
      "locked": true,
      "order": 10,
      "value": "Make your favorite sweets extra special with a coating of freshly melted Chocolate! This chocolate Fondue set makes dessert a fun shared experience, perfect for a romantic meal or for celebrations with friends and family. Always a great gift idea for the chocoholic in your life!"
    },
    "requires_shipping": {
      "slug": "requires_shipping",
      "name": "Requires Shipping",
      "type": "choice",
      "options": {
        "choices": [
          "No",
          "Yes"
        ],
        "default": 1
      },
      "required": true,
      "unique": false,
      "locked": true,
      "order": 11,
      "value": {
        "key": "1",
        "value": "Yes"
      }
    },
    "weight": {
      "slug": "weight",
      "name": "Weight",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": false,
      "unique": false,
      "locked": true,
      "order": 12,
      "value": "234.00"
    },
    "height": {
      "slug": "height",
      "name": "Height",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": false,
      "unique": false,
      "locked": true,
      "order": 13,
      "value": "24.00"
    },
    "width": {
      "slug": "width",
      "name": "Width",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": false,
      "unique": false,
      "locked": true,
      "order": 14,
      "value": "24.00"
    },
    "depth": {
      "slug": "depth",
      "name": "Depth",
      "type": "decimal",
      "options": {
        "decimal_places": 2
      },
      "required": false,
      "unique": false,
      "locked": true,
      "order": 15,
      "value": "32.00"
    },
    "tax_band": {
      "slug": "tax_band",
      "name": "Tax Band",
      "type": "tax-band",
      "options": [],
      "required": false,
      "unique": false,
      "locked": false,
      "order": null,
      "available": {
        "1": "Default",
        "3": "Tax Band 2"
      },
      "value": {
        "id": 1,
        "title": "Default",
        "description": null,
        "rate": "20.00"
      }
    }
  }
}
```
<!--/code-->