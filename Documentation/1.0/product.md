# Products

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Product](#single)
- [Multiple Products](#multiple)
- [Search](#search)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Products are [flows](flows) based data structures that store information relating to your inventory. These items can be added to your [cart](cart) and then sold using the [checkout](checkout) endpoints, specific items can also be set to catalog only to be used for display purposes only.

Products are able to support sizes, colours, etc. using the modifier and variation system, which turns the parent product into a container and only allows the children to be sold. These child products can be totally customised using sku, title, price, stock levels, description and images.

<a name="params"></a>
## Parameters

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
SKU | sku | String | Yes | Yes | -
Product Title | title | String | Yes | No | -
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Price | price | Decimal | Yes | No | Decimal limited to 2 places.
Sale Price | sale_price | Decimal | No | No | Decimal limited to 2 places.
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Category | category | Multiple | Yes | No | Relates to [Categories](category).
Stock Level | stock_level | Integer | Yes | No | -
Stock Status | stock_status | Choice | Yes | No | Choices available are 0 (Unlimited), 1 (In Stock), 2 (Low Stock), 3 (Out Of Stock), 4 (More Stock Ordered), 5 (Discontinued).
Description | description | Text | Yes | No | A WYSIWYG enabled text store.
Requires Shipping | requires_shipping | Choice | Yes | No | Choices available are 0 (No), 1 (Yes).
Weight | weight | Decimal | No | No | Decimal limited to 2 places.
Height | height | Decimal | No | No | Decimal limited to 2 places.
Width | width | Decimal | No | No | Decimal limited to 2 places.
Depth | depth | Decimal | No | No | Decimal limited to 2 places.
Brand | brand | Relationship | No | No | Relates to [Brands](brand).
Tax Band | tax_band | Tax Band | Yes | No | The tax band to use, choices available are 26 (None), 1 (Default).
Catalog Only | catalog_only | Choice | Yes | No | Choices available are 0 (No), 1 (Yes).
Collection | collection | Relationship | No | No | Relates to flow [Collections](collection).

> **Note:** Due to products being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

    {
        "id": 6,
        "order": null,
        "created_at": null,
        "updated_at": "2014-08-12 15:28:20",
        "sku": "PRD_A0002",
        "title": "Conté Sticks",
        "slug": "conte-sticks",
        "price": 9.99,
        "sale_price": 8.99,
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
                    "id": 60,
                    "order": 6,
                    "created_at": null,
                    "updated_at": "2014-08-29 09:37:57",
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
                    "tax_band": null
                }
            }
        },
        "stock_level": 1050,
        "stock_status":
        {
            "value": "In Stock",
            "data":
            {
                "key": "1",
                "value": "In Stock"
            }
        },
        "description": "Drawing with conté sticks is a sure way to achive high contrast, richly pigmented images. This media can also be used to shapen lines as a final stage of a painting's development. ",
        "requires_shipping":
        {
            "value": "Yes",
            "data":
            {
                "key": "1",
                "value": "Yes"
            }
        },
        "weight": 10,
        "height": 10,
        "width": 10,
        "depth": 10,
        "brand": null,
        "collection": null,
        "tax_band":
        {
            "value": "Default",
            "data":
            {
                "id": 1,
                "title": "Default",
                "description": null,
                "rate": 20,
                "created_at": null,
                "updated_at": null
            }
        },
        "catalog_only":
        {
            "value": "No",
            "data":
            {
                "key": "0",
                "value": "No"
            }
        },
        "pricing":
        {
            "formatted":
            {
                "with_tax": "£11.99",
                "without_tax": "£9.99",
                "tax": "£2.00"
            },
            "rounded":
            {
                "with_tax": 11.99,
                "without_tax": 9.99,
                "tax": 2
            },
            "raw":
            {
                "with_tax": 11.988,
                "without_tax": 9.99,
                "tax": 1.998
            }
        },
        "is_variation": false,
        "modifiers":
        [
        ],
        "images":
        [
            {
                "id": 45,
                "name": "artpastels1.jpg",
                "url":
                {
                    "http": "http://commercecdn.com/1/artpastels1.jpg",
                    "https": "https://commercecdn.com/1/artpastels1.jpg"
                },
                "segments":
                {
                    "domain": "commercecdn.com/",
                    "suffix": "1/artpastels1.jpg"
                }
            },
            {
                "id": 47,
                "name": "artpastels2.jpg",
                "url":
                {
                    "http": "http://commercecdn.com/1/artpastels2.jpg",
                    "https": "https://commercecdn.com/1/artpastels2.jpg"
                },
                "segments":
                {
                    "domain": "commercecdn.com/",
                    "suffix": "1/artpastels2.jpg"
                }
            }
        ]
    }

<a name="single"></a>
## Single Product

### Via Id

``` php
$product = Product::Get(<ID>);
```

#### Asynchronous
``` js
moltin.Product.Get('<ID>', function(product) {
    console.log(product);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var product = moltin.Product.Get('<ID>');

if ( product.status === true ) {
    console.log(product.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$product = Product::Find(['slug' => 'example']);
```

#### Asynchronous
``` js
moltin.Product.Find({slug: 'example'}, function(product) {
    console.log(product);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var product = moltin.Product.Find({slug: 'example'});

if ( product.status === true ) {
    console.log(product.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Products

``` php
$products = Product::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Product.List(null, function(product) {
    console.log(product);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var product = moltin.Product.List({status: 1});

if ( product.status === true ) {
    console.log(product.result);
} else {
    // Something went wrong...
}
```

<a name="search"></a>
## Search

``` php
$products = Product::Search(['category' => '6']);
```

#### Asynchronous
``` js
moltin.Product.Search({category: 6, status: 1}, function(products) {
    console.log(products);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var products = moltin.Product.Search({category: 6, status: 1});

if ( products.status === true ) {
    console.log(products.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$product = Product::Create([
    'title'       => 'Featured',
    'slug'        => 'featured',
    'parent'      => null,
    'status'      => 1,
    'description' => 'A selection of featured products'
]);
```

#### Asynchronous
``` js
moltin.Product.Create({
    title:       'Featured',
    slug:        'featured',
    parent:      60,
    status:      1
    description: 'A selection of featured products'
}, function(product) {
    console.log(product);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var product = moltin.Product.Create({
    title:       'Featured',
    slug:        'featured',
    parent:      null,
    status:      1
    description: 'A selection of featured products'
});

if ( product.status === true ) {
    console.log(product.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$product = Product::Edit(<ID>, [
    'title'  => 'Featured - Updated',
    'slug'   => 'featured-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Product.Update('<ID>', {
    title:  'Featured - Updated',
    slug:   'featured-updated',
    status: 0
}, function(product) {
    console.log(product);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var product = moltin.Product.Update('<ID>', {
    title:  'Featured - Updated',
    slug:   'featured-updated',
    status: 0
});

if ( product.status === true ) {
    console.log(product.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
$status = Product::Delete(<ID>);
```

#### Asynchronous
``` js
moltin.Product.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Product.Delete('<ID>');

if ( result.status === true ) {
    // Success
} else {
    // Something went wrong...
}
```

<a name="field"></a>
## Fields

### Create

#### Field Data
``` php
$fields = Product::Fields();
```

#### Pre-built Form
``` php
$fields = Product::Fields(null, true);

echo '<form method="product/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Product.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Product.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Product::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Product::Fields(<ID>, true);

echo '<form method="product/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Product.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Product.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```