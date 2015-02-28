# Categories

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Category](#single)
- [Multiple Categories](#multiple)
- [Tree View](#tree)
- [Create](#create)
- [Update](#update)
- [Ordering & Parents](#order)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Categories are [flows](flows) based data structures that can be organised into parent and child relationships to create a tree structure. This allows categories to not only group [products](product) but to also act as a navigation source.

Categories have a basic data structure containing only the most necissary information; however this can be extended via [flows](flows). This additional data allows you to customise the category to meet the needs of your project, and will automatically be added to your [forge](forge) instance for ease of use.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Parent Category | parent | Relationship | No | No | Relates to flow '**4**'.
Title | title | String | Yes | No | -
Slug | slug | Slug | Yes | Yes | A unique identifier generally used as part of a URL.
Status | status | Choice | Yes | No | Choices available are 0 (Draft), 1 (Live).
Description | description | Text | Yes | No | A WYSIWYG enabled text store.

> **Note:** Due to categories being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a category object, showing the data structure to expect. When a parent is found, the parent element will have the same data structure, with the correct data attached.

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
        "images":
        [
            {
                "id": 531,
                "name": "im.gif",
                "url":
                {
                    "http": "http://commercecdn.com/1/c52e964b-be27-4d01-8ac9-b13cef03cb57.gif",
                    "https": "https://commercecdn.com/1/c52e964b-be27-4d01-8ac9-b13cef03cb57.gif"
                },
                "segments":
                {
                    "domain": "commercecdn.com/",
                    "suffix": "1/c52e964b-be27-4d01-8ac9-b13cef03cb57.gif"
                }
            }
        ]
    }

<a name="single"></a>
## Single Category

### Via Id

``` php
$category = Category::Get(<ID>);
```

#### Asynchronous
``` js
moltin.Category.Get('<ID>', function(category) {
    console.log(category);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var category = moltin.Category.Get('<ID>');

if ( category.status === true ) {
    console.log(category.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$category = Category::Find(['slug' => 'example']);
```

#### Asynchronous
``` js
moltin.Category.Find({slug: 'example'}, function(category) {
    console.log(category);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var category = moltin.Category.Find({slug: 'example'});

if ( category.status === true ) {
    console.log(category.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Categories

``` php
$categories = Category::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Category.List(null, function(category) {
    console.log(category);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var category = moltin.Category.List({status: 1});

if ( category.status === true ) {
    console.log(category.result);
} else {
    // Something went wrong...
}
```

<a name="tree"></a>
## Tree View

``` php
$tree = Category::Tree();
```

#### Asynchronous
``` js
moltin.Category.Tree({parent: 'example'}, function(tree) {
    console.log(tree);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var tree = moltin.Category.Tree({status: 1});

if ( tree.status === true ) {
    console.log(tree.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$category = Category::Create([
    'title'       => 'Featured',
    'slug'        => 'featured',
    'parent'      => null,
    'status'      => 1,
    'description' => 'A selection of featured products'
]);
```

#### Asynchronous
``` js
moltin.Category.Create({
    title:       'Featured',
    slug:        'featured',
    parent:      60,
    status:      1
    description: 'A selection of featured products'
}, function(category) {
    console.log(category);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var category = moltin.Category.Create({
    title:       'Featured',
    slug:        'featured',
    parent:      null,
    status:      1
    description: 'A selection of featured products'
});

if ( category.status === true ) {
    console.log(category.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$category = Category::Edit(<ID>, [
    'title'  => 'Featured - Updated',
    'slug'   => 'featured-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Category.Update('<ID>', {
    title:  'Featured - Updated',
    slug:   'featured-updated',
    status: 0
}, function(category) {
    console.log(category);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var category = moltin.Category.Update('<ID>', {
    title:  'Featured - Updated',
    slug:   'featured-updated',
    status: 0
});

if ( category.status === true ) {
    console.log(category.result);
} else {
    // Something went wrong...
}
```

<a name="order"></a>
## Ordering & Parents

``` php
Category::Order([
    60 => [
        'parent' => null,
        'order'  => 1
    ]
]);
```

#### Asynchronous
``` js
moltin.Category.Order({60: {parent: 3, order: 1}}, function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Category.Order({<ID>: {parent: null, order: 1}});

if ( result.status === true ) {
    // Success
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
$status = Category::Delete(<ID>);
```

#### Asynchronous
``` js
moltin.Category.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Category.Delete('<ID>');

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
$fields = Category::Fields();
```

#### Pre-built Form
``` php
$fields = Category::Fields(null, true);

echo '<form method="category/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Category.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Category.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Category::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Category::Fields(<ID>, true);

echo '<form method="category/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Category.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Category.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```