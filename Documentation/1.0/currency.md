# Currencies

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Set Currency](#set)
- [Single Currency](#single)
- [Multiple Currencies](#multiple)
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
Code | code | String | Yes | Yes | -
Title | title | String | Yes | No | -
Enabled? | enabled | Choice | Yes | No | Choices available are 0 (No), 1 (Yes).
Modifier | modifier | String | No | No | -
Exchange rate | exchange_rate | Decimal | No | No | Decimal limited to 5 places.
Format | format | String | Yes | No | -
Decimal Point | decimal_point | String | No | No | -
Thousand Point | thousand_point | String | No | No | -
Rounding | rounding | Choice | No | No | Choices available are full (Round up to next full number), 50 (Round up to nearest .50), 99 (Round up to nearest .99).

<a name="object"></a>
## Object

	{
	    "id": 17,
	    "code": "USD",
	    "title": "US Dollar",
	    "enabled": true,
	    "modifier": "++0",
	    "exchange_rate": 1.65,
	    "format": "${price}",
	    "decimal_point": ".",
	    "thousand_point": ",",
	    "rounding": null,
	    "default": false,
	    "created_at": null,
	    "updated_at": null
	}

<a name="set"></a>
## Set Currency

To set the currency for any calls simple use the example below, passing in your currency code (USD, GBP, etc) and this will automatically change the currency for all subsequent calls.

``` php
$currency = Currency::Set('<CODE>');
```

#### Asynchronous
``` js
moltin.Currency.Set('<CODE>');
```

> **Note:** The currency selected must be added to your store before available to be switched.

<a name="single"></a>
## Single Currency

### Via Id

``` php
$currency = Currency::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Currency.Get('<ID>', function(currency) {
    console.log(currency);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var currency = moltin.Currency.Get('<ID>');

if ( currency.status === true ) {
    console.log(currency.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$currency = Currency::Find(['slug' => 'example-currency']);
```

#### Asynchronous
``` js
moltin.Currency.Find({slug: 'example-currency'}, function(currency) {
    console.log(currency);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var currency = moltin.Currency.Find({slug: 'example-currency'});

if ( currency.status === true ) {
    console.log(currency.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Currencies

``` php
$currencies = Currency::Listing(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Currency.List(null, function(currencies) {
    console.log(currencies);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var currencies = moltin.Currency.List({status: 1});

if ( currencies.status === true ) {
    console.log(currencies.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$currency = Currency::Create([
    'title'       => 'Example Currency',
    'slug'        => 'example-currency',
    'status'      => 1,
    'description' => 'A selection of example currencies products'
]);
```

#### Asynchronous
``` js
moltin.Currency.Create({
    title:       'Example Currency',
    slug:        'example-currency',
    status:      1
    description: 'A selection of example currencies products'
}, function(currency) {
    console.log(currency);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var currency = moltin.Currency.Create({
    title:       'Example Currency',
    slug:        'example-currency',
    status:      1
    description: 'A selection of example currencies products'
});

if ( currency.status === true ) {
    console.log(currency.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$currency = Currency::Edit('<ID>', [
    'title'  => 'Example Currency - Updated',
    'slug'   => 'example-currency-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Currency.Update('<ID>', {
    title:  'Example Currency - Updated',
    slug:   'example-currency-updated',
    status: 0
}, function(currency) {
    console.log(currency);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var currency = moltin.Currency.Update('<ID>', {
    title:  'Example Currency - Updated',
    slug:   'example-currency-updated',
    status: 0
});

if ( currency.status === true ) {
    console.log(currency.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Currency::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Currency.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Currency.Delete('<ID>');

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
$fields = Currency::Fields();
```

#### Pre-built Form
``` php
$fields = Currency::Fields(null, true);

echo '<form method="currency/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Currency.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Currency.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Currency::Fields(<ID>);
```

#### Pre-built Form
``` php
$fields = Currency::Fields(<ID>, true);

echo '<form method="currency/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Currency.Fields('<ID>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Currency.Fields('<ID>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
