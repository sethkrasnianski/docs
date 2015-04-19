# Addressess

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Address](#single)
- [Multiple Addresses](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Addresses are [flows](flow) based data structures that are tied to [customers](customers) and consumed by [orders](orders).

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Save address as | save_as | String | No | No | -
First Name | first_name | String | Yes | No | -
Last Name | last_name | String | Yes | No | -
Address Line 1 | address_1 | String | Yes | No | -
Address Line 2 | address_2 | String | No | No | -
Postcode | postcode | String | Yes | No | -
Country | country | Country | Yes | No | -
Company Name | company | String | No | No | -
City | city | String | No | No | -
Customer | customer | Relationship | No | No | Relates to [Customers](customer).
Phone | phone | String | No | No | -
County | county | String | No | No | -
Instructions | instructions | Text | No | No | -

> **Note:** Due to addresses being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of an address object, showing the data structure to expect.

    {
        "id": "6824",
        "order": null,
        "created_at": "2014-10-03 16:18:02",
        "updated_at": "2014-10-03 16:18:02",
        "save_as": "Home",
        "first_name": "Homer",
        "last_name": "Simpson",
        "address_1": "742 Evergreen Terrace",
        "address_2": "",
        "postcode": "58008",
        "country":
        {
            "value": "United States",
            "data":
            {
                "code": "US",
                "name": "United States"
            }
        },
        "company": "",
        "city": "Springfield",
        "customer":
        {
            "value": "CUSTOMER EMAIL",
            "data": <a href="customer">[CUSTOMER OBJECT]</a>
        },
        "phone": "(939) 555-0113",
        "county": "Unknown",
        "instructions": "Beware of the dog"
    }

<a name="single"></a>
## Single Address

### Via Id

``` php
$address = Address::Get('<CUSTOMER ID>', '<ID>');
```

#### Asynchronous
``` js
moltin.Address.Get('<CUSTOMER ID>', '<ID>', function(address) {
    console.log(address);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var address = moltin.Address.Get('<CUSTOMER ID>', '<ID>');

if ( address.status === true ) {
    console.log(address.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$address = Address::Find('<CUSTOMER ID>', ['city' => 'example']);
```

#### Asynchronous
``` js
moltin.Address.Find('<CUSTOMER ID>', {city: 'example'}, function(address) {
    console.log(address);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var address = moltin.Address.Find('<CUSTOMER ID>', {city: 'example'});

if ( address.status === true ) {
    console.log(address.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Addresses

``` php
$addresses = Address::Listing('<CUSTOMER ID>', ['city' => 'example']);
```

#### Asynchronous
``` js
moltin.Address.List('<CUSTOMER ID>', null, function(addresses) {
    console.log(addresses);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var addresses = moltin.Address.List('<CUSTOMER ID>', {city: 'example'});

if ( addresses.status === true ) {
    console.log(addresses.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$address = Address::Create('<CUSTOMER ID>', [
    'title'       => 'Example Address',
    'slug'        => 'example-address',
    'status'      => 1,
    'description' => 'A selection of example addresses products'
]);
```

#### Asynchronous
``` js
moltin.Address.Create('<CUSTOMER ID>', {
    title:       'Example Address',
    slug:        'example-address',
    status:      1
    description: 'A selection of example addresses products'
}, function(address) {
    console.log(address);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var address = moltin.Address.Create('<CUSTOMER ID>', {
    title:       'Example Address',
    slug:        'example-address',
    status:      1
    description: 'A selection of example addresses products'
});

if ( address.status === true ) {
    console.log(address.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$address = Address::Edit('<CUSTOMER ID>', '<ID>', [
    'title'  => 'Example Address - Updated',
    'slug'   => 'example-address-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Address.Update('<CUSTOMER ID>', '<ID>', {
    title:  'Example Address - Updated',
    slug:   'example-address-updated',
    status: 0
}, function(address) {
    console.log(address);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var address = moltin.Address.Update('<CUSTOMER ID>', '<ID>', {
    title:  'Example Address - Updated',
    slug:   'example-address-updated',
    status: 0
});

if ( address.status === true ) {
    console.log(address.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Address::Delete('<CUSTOMER ID>', '<ID>');
```

#### Asynchronous
``` js
moltin.Address.Delete('<CUSTOMER ID>', '<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Address.Delete('<CUSTOMER ID>', '<ID>');

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
$fields = Address::Fields('<CUSTOMER ID>');
```

#### Pre-built Form
``` php
$fields = Address::Fields('<CUSTOMER ID>', null, true);

echo '<form method="address/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Address.Fields('<CUSTOMER ID>', null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Address.Fields('<CUSTOMER ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Address::Fields('<CUSTOMER ID>', '<ID>'');
```

#### Pre-built Form
``` php
$fields = Address::Fields('<CUSTOMER ID>', '<ID>', true);

echo '<form method="address/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Address.Fields('<CUSTOMER ID>', '<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Address.Fields('<CUSTOMER ID>', '<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
