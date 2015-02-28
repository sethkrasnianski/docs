# Cart

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Insert Item](#insert-item)
- [Insert Variation](#insert-variation)
- [Is Item in Cart?](#in-cart)
- [Get Item](#get-item)
- [Update Item](#update-item)
- [Remove Item](#remove-item)
- [Contents](#contents)
- [Delete Cart & Contents](#delete)

<a name="introduction"></a>
## Introduction

The cart allows users to register their interest in items and store them to be bought now or later. The cart system can have normal products, variatons and custom items added to it, all data added to a cart is stored and available whenever it or an [order](order) is retrieved.

<a name="params"></a>
## Parameters

To insert an item into your cart you must pass through two items, id and quantity. Modifiers can also be passed through to insert a child product if it has them. You can also pass in a range of custom data which will be kept if your store requires it.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
ID | id | Integer | Yes | No | The id of the product, or parent product.
Quantity | quantity | Integer | Yes | No | The number of the product to add.
Modifier | modifier | Array | No | No | An array (modifier[mod_id]=variation_id) or modifiers and variations of the parent product.

<a name="object"></a>
## Object

    {
        "contents": <a href="product#object">[PRODUCT OBJECT ARRAY]</a>,
        "discount_coe": null,
        "total_items": 6,
        "total_unique_items": 6,
        "totals":
        {
            "formatted":
            {
                "with_tax": "$71.93",
                "without_tax": "$59.94"
            },
            "rounded":
            {
                "with_tax": 71.93,
                "without_tax": 59.94
            },
            "raw":
            {
                "with_tax": 71.928,
                "without_tax": 59.94
            }
        },
        "currency": <a href="currency#object">[CURRENCY OBJECT]</a>
    }

<a name="insert-item"></a>
## Insert Item

``` php
$cart = Cart::Insert('<ID>', '<QUANTITY>');
```

#### Asynchronous
``` js
moltin.Cart.Insert('<ID>', '<QUANTITY>', null, function(cart) {
    console.log(cart);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var cart = moltin.Cart.Insert('<ID>', '<QUANTITY>');

if ( cart.status === true ) {
    console.log(cart.result);
} else {
    // Something went wrong...
}
```

<a name="insert-variation"></a>
## Insert Variation

``` php
$cart = Cart::Insert('<ID>', '<QUANTITY>', [
    '<MODIFIER ID>' => '<VARIATION ID>'
]);
```

#### Asynchronous
``` js
moltin.Cart.Insert('<ID>', '<QUANTITY>', {'<MODIFIER ID>': '<VARIATION ID>'}, function(cart) {
    console.log(cart);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var cart = moltin.Cart.Insert('<ID>', '<QUANTITY>', {'<MODIFIER ID>': '<VARIATION ID>'});

if ( cart.status === true ) {
    console.log(cart.result);
} else {
    // Something went wrong...
}
```

<a name="in-cart"></a>
## Is Item in Cart?

``` php
$item = Cart::InCart('<ID>');
```

#### Asynchronous
``` js
moltin.Cart.InCart('<ID>', function(item) {
    // Found...
}, function(error) {
    // Not found...
});
```

#### Synchronous
``` js
var item = moltin.Cart.InCart('<ID>');

if ( item.status === true ) {
    // Found...
} else {
    // Not found...
}
```

<a name="get-item"></a>
## Get Item

``` php
$item = Cart::Item('<IDENTIFIER>');
```

#### Asynchronous
``` js
moltin.Cart.Item('<IDENTIFIER>', function(item) {
    console.log(item);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var item = moltin.Cart.InCart('<IDENTIFIER>');

if ( item.status === true ) {
    console.log(item.result);
} else {
    // Not found...
}
```

> **Note:** When referencing items in the cart you must use their unique identifier and not their ID.

<a name="update-item"></a>
## Update Item

``` php
$item = Cart::Update('<IDENTIFIER>', [
    'quantity' => 3
]);
```

#### Asynchronous
``` js
moltin.Cart.Update('<IDENTIFIER>', {
    quantity: 3
}, function(item) {
    console.log(item);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var item = moltin.Cart.Update('<IDENTIFIER>', {
    quantity: 3
});

if ( item.status === true ) {
    console.log(item.result);
} else {
    // Something went wrong...
}
```

<a name="remove-item"></a>
## Remove Item

``` php
Cart::Remove('<IDENTIFIER>');
```

#### Asynchronous
``` js
moltin.Cart.Remove('<IDENTIFIER>', function() {
    // Everything is awesome...
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Cart.Remove('<IDENTIFIER>');

if ( result.status === true ) {
    // Everything is awesome...
} else {
    // Something went wrong...
}
```

<a name="contents"></a>
## Contents

``` php
$items = Cart::Contents();
```

#### Asynchronous
``` js
moltin.Cart.Contents(function(items) {
    console.log(items);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var items = moltin.Cart.Contents();

if ( items.status === true ) {
    console.log(items.result);
} else {
    // Not found...
}
```

<a name="delete"></a>
## Delete Cart & Contents

``` php
Cart::Delete();
```

#### Asynchronous
``` js
moltin.Cart.Delete(function() {
    // Everything is awesome...
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Cart.Delete();

if ( result.status === true ) {
    // Everything is awesome...
} else {
    // Something went wrong...
}
```
