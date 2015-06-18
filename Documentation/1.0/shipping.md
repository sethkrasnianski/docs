# Shipping

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Shipping](#single)
- [Multiple Shipping](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)

<a name="introduction"></a>
## Introduction

Shipping are [flows](flows) based data structures.

Shipping has a basic data structure containing only the most necessary information; however this can be extended via [flows](flows). This additional data allows you to customise shipping to meet the needs of your project, and will automatically be added to your [forge](forge) instance for ease of use.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Title | title | String | Yes | No | -
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Company | company | String | Yes | No | -
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Minimum Price | price_min | Decimal | No | No | Decimal limited to 2 places.
Maximum Price | price_max | Decimal | No | No | Decimal limited to 2 places.
Minimum Weight | weight_min | Decimal | No | No | Decimal limited to 2 places.
Maximum Weight | weight_max | Decimal | No | No | Decimal limited to 2 places.
Description | description | Text | No | No | -
Tax Band | tax_band | Tax Band | Yes | No | The tax band to use, choices available are 57 (Default), 58 (None).
Price | price | Decimal | Yes | No | Decimal limited to 2 places.

> **Note:** Due to shipping being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a shipping object, showing the data structure to expect. When a parent is found, the parent element will have the same data structure, with the correct data attached. This can be repeated further if the parent has a parent, and so on.

    {
        "id": "154",
        "title": "Free Shipping",
        "slug": "free",
        "company": "FedEx",
        "status": {
            "key": "1",
            "value": "Live"
        },
        "price": "0",
        "price_min": "10.00",
        "price_max": "100.00",
        "weight_min": "10.00",
        "weight_max": "100.00",
        "description": "Free shipping on orders between £10 and £100",
        "tax_band": {
            "id": 1,
            "title": "Default",
            "description": null,
            "rate": "20.00"
        }
    }

<a name="single"></a>
## Single Shipping

### Via Id

``` php
$shipping = Shipping::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Shipping.Get('<ID>', function(shipping) {
    console.log(shipping);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var shipping = moltin.Shipping.Get('<ID>');

if ( shipping.status === true ) {
    console.log(shipping.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$shipping = Shipping::Find(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Shipping.Find({status: '1'}, function(shipping) {
    console.log(shipping);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var shipping = moltin.Shipping.Find({status: '1'});

if ( shipping.status === true ) {
    console.log(shipping.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Shipping

``` php
$shipping = Shipping::Listing();
```

#### Asynchronous
``` js
moltin.Shipping.List(null, function(shipping) {
    console.log(shipping);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var shipping = moltin.Shipping.List();

if ( shipping.status === true ) {
    console.log(shipping.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$shipping = Shipping::Create([
    'title'       => 'Free Shipping',
    'slug'        => 'free',
    'company'     => 'Moltin',
    'status'      => 1,
    'description' => 'Free shipping from FedEx',
    'price'       => '10',
    'tax_band'    => 1
]);
```

#### Asynchronous
``` js
moltin.Shipping.Create({
    title:      'Free Shipping',
    slug:       'free',
    company:    'Moltin',
    status:      1,
    description: 'Free shipping from FedEx',
    price:       '10',
    tax_band:    1
}, function(shipping) {
    console.log(shipping);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var shipping = moltin.Shipping.Create({
    title:      'Free Shipping',
    slug:       'free',
    company:    'Moltin',
    status:      1,
    description: 'Free shipping from FedEx',
    price:       '10',
    tax_band:    1
});

if ( shipping.status === true ) {
    console.log(shipping.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$shipping = Shipping::Edit(<ID>, [
    'title'       => 'Free Shipping',
    'slug'        => 'free',
    'company'     => 'Moltin',
    'status'      => 1,
    'description' => 'Free shipping from FedEx',
    'price'       => '20',
    'tax_band'    => 1
]);
```

#### Asynchronous
``` js
moltin.Shipping.Update('<ID>', {
    title:      'Free Shipping',
    slug:       'free',
    company:    'Moltin',
    status:      1,
    description: 'Free shipping from FedEx',
    price:       '20',
    tax_band:    1
}, function(shipping) {
    console.log(shipping);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var shipping = moltin.Shipping.Update('<ID>', {
    title:      'Free Shipping',
    slug:       'free',
    company:    'Moltin',
    status:      1,
    description: 'Free shipping from FedEx',
    price:       '20',
    tax_band:    1
});

if ( shipping.status === true ) {
    console.log(shipping.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Shipping::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Shipping.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Shipping.Delete('<ID>');

if ( result.status === true ) {
    // Success
} else {
    // Something went wrong...
}
```
