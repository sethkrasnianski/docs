# Entries

- [Introduction](#introduction)
- [Single Entry](#single)
- [Multiple Entries](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Entries are rows of data stored in a [flow](flow) and can be everything from a product to a customer. Each of these items can be customised via the [forge](forge) dashboard or directly via the api itself.

> **Note:** Entries are custom to their flow and each object will be different, however each will contain an id, order, created_at, and updated_at value.

<a name="single"></a>
## Single Entry

### Via Id

``` php
$entry = Entry::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Entry.Get('<ID>', function(entry) {
    console.log(entry);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var entry = moltin.Entry.Get('<ID>');

if ( entry.status === true ) {
    console.log(entry.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$entry = Entry::Find(['slug' => 'example-entry']);
```

#### Asynchronous
``` js
moltin.Entry.Find({slug: 'example-entry'}, function(entry) {
    console.log(entry);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var entry = moltin.Entry.Find({slug: 'example-entry'});

if ( entry.status === true ) {
    console.log(entry.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Entries

``` php
$entries = Entry::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Entry.List(null, function(entries) {
    console.log(entries);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var entries = moltin.Entry.List({status: 1});

if ( entries.status === true ) {
    console.log(entries.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$entry = Entry::Create([
    'title'       => 'Example Entry',
    'slug'        => 'example-entry',
    'status'      => 1,
    'description' => 'A selection of example entries products'
]);
```

#### Asynchronous
``` js
moltin.Entry.Create({
    title:       'Example Entry',
    slug:        'example-entry',
    status:      1
    description: 'A selection of example entries products'
}, function(entry) {
    console.log(entry);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var entry = moltin.Entry.Create({
    title:       'Example Entry',
    slug:        'example-entry',
    status:      1
    description: 'A selection of example entries products'
});

if ( entry.status === true ) {
    console.log(entry.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$entry = Entry::Edit('<ID>', [
    'title'  => 'Example Entry - Updated',
    'slug'   => 'example-entry-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Entry.Update('<ID>', {
    title:  'Example Entry - Updated',
    slug:   'example-entry-updated',
    status: 0
}, function(entry) {
    console.log(entry);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var entry = moltin.Entry.Update('<ID>', {
    title:  'Example Entry - Updated',
    slug:   'example-entry-updated',
    status: 0
});

if ( entry.status === true ) {
    console.log(entry.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Entry::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Entry.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Entry.Delete('<ID>');

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
$fields = Entry::Fields();
```

#### Pre-built Form
``` php
$fields = Entry::Fields(null, true);

echo '<form method="entry/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Entry.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Entry.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Entry::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Entry::Fields(<ID>, true);

echo '<form method="entry/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Entry.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Entry.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
