# Free Tshirt

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Order](#order)

<a name="introduction"></a>
## Introduction

OMG YOU FOUND IT!!!!111 Here's the deal, want to send you a free tshirt and some small extras to say thanks for being awesome. All you have to do is call the endpoint below with your email, shipping address and shirt style and we'll take care of the rest!

> **Note:** This endpoint is only available in v1 of the API, please make sure to use the correct version otherwise your order will not be recieved.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this item, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Style | style | String | Yes | No | The style must match gray, red, or purple
Size | size | String | Yes | No | The size must match s, m, l, xl, or xxl
First Name | first_name | String | Yes | No | First name of recipient
Last Name | last_name | String | Yes | No | Last name of recipient
Email | email | String | Yes | Yes | Email to recieve order and shipping confirmation
Ship To | ship_to | Array | Yes | No | [Address object](/{{ version }}/address/{{ language }}#object) for order to be shipped to

<a name="object"></a>
## Object

> **Note:** Unlike other endpoints there's no object here, we'll simply return true or false and an error array. Within a few minutes of getting a true response you'll get an email to confirm your order has been placed and will be dispatched soon.

<a name="order"></a>
## Order

``` php
$order = Moltin::Post('tshirt', [
    'style'      => '<gray, red, or purple>',
    'size'       => '<s, m, l, xl, or xxl>',
    'first_name' => '',
    'last_name'  => '',
    'email'      => '',
    'ship_to'    => [
        'address_1' => '',
        'address_2' => '',
        'city'      => '',
        'county'    => '',
        'postcode'  => '',
        'country'   => ''
    ]
]);
```

#### Asynchronous
``` js
moltin.Request('tshirt', 'POST', {
    style:      '<gray, red, or purple>',
    size:       '<s, m, l, xl, or xxl>',
    first_name: '',
    last_name:  '',
    email:      '',
    ship_to:    {
        address_1: '',
        address_2: '',
        city:      '',
        county:    '',
        postcode:  '',
        country:   ''
    }
}, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Request('tshirt', 'POST', {
    style:      '<gray, red, or purple>',
    size:       '<s, m, l, xl, or xxl>',
    first_name: '',
    last_name:  '',
    email:      '',
    ship_to:    {
        address_1: '',
        address_2: '',
        city:      '',
        county:    '',
        postcode:  '',
        country:   ''
    }
});

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```
