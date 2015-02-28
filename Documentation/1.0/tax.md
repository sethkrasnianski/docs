# Taxes

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Tax](#single)
- [Multiple Taxes](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)

<a name="introduction"></a>
## Introduction

Taxes!

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Title | title | String | Yes | No | The title of this tax band.
Description | description | String | No | No | A short description of this tax band.
Rate | rate | Decimal | Yes | No | The default tax rate (can be changed on a per-currency basis).

<a name="object"></a>
## Object

Below is an example of a tax object, showing the data structure to expect.

    {
        "id": 8,
        "title": "My awesome tax band",
        "description": "Awesome products are charged tax at 99% right?...",
        "rate": "99.00",
        "currencies": <a href="currency#object">[CURRENCY OBJECT ARRAY]</a>
    }

<a name="single"></a>
## Single Tax

### Via Id

``` php
$tax = Tax::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Tax.Get('<ID>', function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.Get('<ID>');

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```

#### Asynchronous
``` js
moltin.Tax.Find({slug: 'example'}, function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.Find({slug: 'example'});

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Taxes

``` php
$tax = Tax::Listing(['limit' => '10', 'offset' => '2']);
```

#### Asynchronous
``` js
moltin.Tax.List({limit: 10, offset: 2}, function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.List({limit: 10, offset: 2});

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$tax = Tax::Create([
    'title' => 'Tax Band 1',
    'description' => 'Tax Band specific to area 1',
    'rate' => 20
]);
```

#### Asynchronous
``` js
moltin.Tax.Create({
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 20
}, function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.Create({
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 20
});

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$tax = Tax::Edit('<ID>', [
    'title' => 'Tax Band 1',
    'description' => 'Tax Band specific to area 1',
    'rate' => 30
]);
```

#### Asynchronous
``` js
moltin.Tax.Update('<ID>', {
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 30
}, function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.Update('<ID>', {
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 30
});

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
$tax = Tax::Edit('<ID>', [
    'title' => 'Tax Band 1',
    'description' => 'Tax Band specific to area 1',
    'rate' => 30
]);
```

#### Asynchronous
``` js
moltin.Tax.Update('<ID>', {
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 30
}, function(tax) {
    console.log(tax);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tax = moltin.Tax.Update('<ID>', {
    title: 'Tax Band 1',
    description: 'Tax Band specific to area 1',
    rate: 30
});

if ( tax.status === true ) {
    console.log(tax.result);
} else {
    // Something went wrong...
}
```