# Gateways

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Availability](#available)
- [Single Gateway](#single)
- [Multiple Gateways](#multiple)
- [Update](#update)
- [Enable/Disable](#enable-disable)
- [Fields](#fields)

<a name="introduction"></a>
## Introduction

TODO

<a name="params"></a>
## Parameters

TODO

<a name="object"></a>
## Object

TODO

<a name="available"></a>
## Availability

Below is a list of the available payment gateways and the support they offer

Name | authorize | complete_authorize | capture | purchase | complete_purchase | refund | void
---- | --------- | ------------------ | ------- | -------- | ----------------- | ------ | ----
[Stripe](https://stripe.com) | Yes | Yes | Yes | Yes | Yes | Yes | Yes

> **Note:** Finish up this list, automate if possible.

<a name="single"></a>
## Single Gateway

``` php
$gateway = Gateway::Get('<SLUG>');
```

#### Asynchronous
``` js
moltin.Gateway.Get('<SLUG>', function(gateway) {
    console.log(gateway);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var gateway = moltin.Gateway.Get('<SLUG>');

if ( gateway.status === true ) {
    console.log(gateway.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Gateways

``` php
$gateways = Gateway::Listing();
```

#### Asynchronous
``` js
moltin.Gateway.List(null, function(gateways) {
    console.log(gateways);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var gateways = moltin.Gateway.List({status: 1});

if ( gateways.status === true ) {
    console.log(gateways.result);
} else {
    // Something went wrong...
}
```
<a name="update"></a>
## Update

``` php
$gateway = Gateway::Edit('<SLUG>', [
    'title'  => 'Example Gateway - Updated',
    'slug'   => 'example-gateway-updated',
    'status' => 0
]);
```

#### Asynchronous
``` js
moltin.Gateway.Update('<SLUG>', {
    title:  'Example Gateway - Updated',
    slug:   'example-gateway-updated',
    status: 0
}, function(gateway) {
    console.log(gateway);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var gateway = moltin.Gateway.Update('<SLUG>', {
    title:  'Example Gateway - Updated',
    slug:   'example-gateway-updated',
    status: 0
});

if ( gateway.status === true ) {
    console.log(gateway.result);
} else {
    // Something went wrong...
}
```

<a name="enable-disable"></a>
## Enable/Disable

### Enable

``` php
Gateway::Enable('<SLUG>');
```

### Disable

``` php
Gateway::Disable('<SLUG>');
```

<a name="field"></a>
## Fields

### Create

#### Field Data
``` php
$fields = Gateway::Fields();
```

#### Pre-built Form
``` php
$fields = Gateway::Fields(null, true);

echo '<form method="gateway/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Gateway.Fields(null, function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Gateway.Fields();

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```

### Update

#### Field Data
``` php
$fields = Gateway::Fields(<SLUG>);
```

#### Pre-built Form
``` php
$fields = Gateway::Fields(<SLUG>, true);

echo '<form method="gateway/edit/<SLUG>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```

#### Asynchronous
``` js
moltin.Gateway.Fields('<SLUG>', function(fields) {
    console.log(fields);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var fields = moltin.Gateway.Fields('<SLUG>');

if ( fields.status === true ) {
    console.log(fields.result);
} else {
    // Something went wrong...
}
```
