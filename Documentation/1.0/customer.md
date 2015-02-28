# Customers

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Customer](#single)
- [Multiple Customers](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

TODO

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
First Name | first_name | String | Yes | No | -
Last Name | last_name | String | Yes | No | -
Email Address | email | Email | Yes | Yes | -
Group | group | Relationship | No | No | Relates to [Customer Groups]().

> **Note:** Due to customers being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a customer object, showing the data structure to expect.

    {
        "id": "6819",
        "order": null,
        "created_at": "2014-10-03 16:17:49",
        "updated_at": "2014-10-03 16:17:49",
        "first_name": "Homer",
        "last_name": "Simpson",
        "email": "hjsimpson@springfield.net",
        "group": null,
        "history":
        {
            "orders": 3,
            "value": "211.89",
            "addresses": 4
        }
    }

<a name="single"></a>
## Single Customer

### Via Id

``` php
$customer = Customer::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Customer.Get('<ID>', function(customer) {
    console.log(customer);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var customer = moltin.Customer.Get('<ID>');

if ( customer.status === true ) {
    console.log(customer.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$customer = Customer::Find(['slug' => 'example-customer']);
```

#### Asynchronous
``` js
moltin.Customer.Find({slug: 'example-customer'}, function(customer) {
    console.log(customer);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var customer = moltin.Customer.Find({slug: 'example-customer'});

if ( customer.status === true ) {
    console.log(customer.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Customers

``` php
$customers = Customer::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Customer.List(null, function(customers) {
    console.log(customers);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var customers = moltin.Customer.List({status: 1});

if ( customers.status === true ) {
    console.log(customers.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$customer = Customer::Create([
    'title'       => 'Example Customer',
    'slug'        => 'example-customer',
    'status'      => 1,
    'description' => 'A selection of example customers products'
]);
```

#### Asynchronous
``` js
moltin.Customer.Create({
    title:       'Example Customer',
    slug:        'example-customer',
    status:      1
    description: 'A selection of example customers products'
}, function(customer) {
    console.log(customer);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var customer = moltin.Customer.Create({
    title:       'Example Customer',
    slug:        'example-customer',
    status:      1
    description: 'A selection of example customers products'
});

if ( customer.status === true ) {
    console.log(customer.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$customer = Customer::Edit('<ID>', [
    'title'  => 'Example Customer - Updated',
    'slug'   => 'example-customer-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Customer.Update('<ID>', {
    title:  'Example Customer - Updated',
    slug:   'example-customer-updated',
    status: 0
}, function(customer) {
    console.log(customer);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var customer = moltin.Customer.Update('<ID>', {
    title:  'Example Customer - Updated',
    slug:   'example-customer-updated',
    status: 0
});

if ( customer.status === true ) {
    console.log(customer.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Customer::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Customer.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Customer.Delete('<ID>');

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
$fields = Customer::Fields();
```

#### Pre-built Form
``` php
$fields = Customer::Fields(null, true);

echo '<form method="customer/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Customer.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Customer.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Customer::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Customer::Fields(<ID>, true);

echo '<form method="customer/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Customer.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Customer.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

