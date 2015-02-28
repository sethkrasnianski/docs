# Brands

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Brand](#single)
- [Multiple Brands](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Brands are [flows](flows) based data structures that can be used as a descriptor for [products](product).

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Brand Name | title | String | Yes | No | -
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Description | description | Text | Yes | No | A WYSIWYG enabled text store.

> **Note:** Due to brands being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a brand object, showing the data structure to expect.

    {
        "id": "98",
        "title": "Example Brand",
        "slug": "example-brand",
        "status":
        {
            "key": "1",
            "value": "Live"
        },
        "description": "Example brand description",
        "images": []
    }

<a name="single"></a>
## Single Brand

### Via Id

``` php
$brand = Brand::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Brand.Get('<ID>', function(brand) {
    console.log(brand);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var brand = moltin.Brand.Get('<ID>');

if ( brand.status === true ) {
    console.log(brand.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$brand = Brand::Find(['slug' => 'example-brand']);
```

#### Asynchronous
``` js
moltin.Brand.Find({slug: 'example-brand'}, function(brand) {
    console.log(brand);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var brand = moltin.Brand.Find({slug: 'example-brand'});

if ( brand.status === true ) {
    console.log(brand.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Brands

``` php
$brands = Brand::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Brand.List(null, function(brands) {
    console.log(brands);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var brands = moltin.Brand.List({status: 1});

if ( brands.status === true ) {
    console.log(brands.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$brand = Brand::Create([
    'title'       => 'Example Brand',
    'slug'        => 'example-brand',
    'status'      => 1,
    'description' => 'A selection of example brands products'
]);
```

#### Asynchronous
``` js
moltin.Brand.Create({
    title:       'Example Brand',
    slug:        'example-brand',
    status:      1
    description: 'A selection of example brands products'
}, function(brand) {
    console.log(brand);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var brand = moltin.Brand.Create({
    title:       'Example Brand',
    slug:        'example-brand',
    status:      1
    description: 'A selection of example brands products'
});

if ( brand.status === true ) {
    console.log(brand.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$brand = Brand::Edit('<ID>', [
    'title'  => 'Example Brand - Updated',
    'slug'   => 'example-brand-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Brand.Update('<ID>', {
    title:  'Example Brand - Updated',
    slug:   'example-brand-updated',
    status: 0
}, function(brand) {
    console.log(brand);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var brand = moltin.Brand.Update('<ID>', {
    title:  'Example Brand - Updated',
    slug:   'example-brand-updated',
    status: 0
});

if ( brand.status === true ) {
    console.log(brand.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Brand::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Brand.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Brand.Delete('<ID>');

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
$fields = Brand::Fields();
```

#### Pre-built Form
``` php
$fields = Brand::Fields(null, true);

echo '<form method="brand/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Brand.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Brand.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Brand::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Brand::Fields(<ID>, true);

echo '<form method="brand/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Brand.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Brand.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
