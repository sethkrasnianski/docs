# Collections

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Collection](#single)
- [Multiple Collections](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Collections are [flows](flows) based data structures that can be used as a descriptor for [products](product).

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Collection Name | title | String | Yes | No | -
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Description | description | Text | Yes | No | A WYSIWYG enabled text store.

> **Note:** Due to collections being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a collection object, showing the data structure to expect.

    {
        "id": "98",
        "title": "Example Collection",
        "slug": "example-collection",
        "status":
        {
            "key": "1",
            "value": "Live"
        },
        "description": "Example collection description",
        "images": []
    }

<a name="single"></a>
## Single Collection

### Via Id

``` php
$collection = Collection::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Collection.Get('<ID>', function(collection) {
    console.log(collection);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var collection = moltin.Collection.Get('<ID>');

if ( collection.status === true ) {
    console.log(collection.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$collection = Collection::Find(['slug' => 'example-collection']);
```

#### Asynchronous
``` js
moltin.Collection.Find({slug: 'example-collection'}, function(collection) {
    console.log(collection);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var collection = moltin.Collection.Find({slug: 'example-collection'});

if ( collection.status === true ) {
    console.log(collection.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Collections

``` php
$collections = Collection::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Collection.List(null, function(collections) {
    console.log(collections);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var collections = moltin.Collection.List({status: 1});

if ( collections.status === true ) {
    console.log(collections.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$collection = Collection::Create([
    'title'       => 'Example Collection',
    'slug'        => 'example-collection',
    'status'      => 1,
    'description' => 'A selection of example collections products'
]);
```

#### Asynchronous
``` js
moltin.Collection.Create({
    title:       'Example Collection',
    slug:        'example-collection',
    status:      1
    description: 'A selection of example collections products'
}, function(collection) {
    console.log(collection);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var collection = moltin.Collection.Create({
    title:       'Example Collection',
    slug:        'example-collection',
    status:      1
    description: 'A selection of example collections products'
});

if ( collection.status === true ) {
    console.log(collection.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$collection = Collection::Edit('<ID>', [
    'title'  => 'Example Collection - Updated',
    'slug'   => 'example-collection-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Collection.Update('<ID>', {
    title:  'Example Collection - Updated',
    slug:   'example-collection-updated',
    status: 0
}, function(collection) {
    console.log(collection);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var collection = moltin.Collection.Update('<ID>', {
    title:  'Example Collection - Updated',
    slug:   'example-collection-updated',
    status: 0
});

if ( collection.status === true ) {
    console.log(collection.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Collection::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Collection.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Collection.Delete('<ID>');

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
$fields = Collection::Fields();
```

#### Pre-built Form
``` php
$fields = Collection::Fields(null, true);

echo '<form method="collection/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Collection.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Collection.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Collection::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Collection::Fields(<ID>, true);

echo '<form method="collection/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Collection.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Collection.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
