# Checkout

- [Introduction](#introduction)
- [Cart Options](#options)
- [Create Order from Cart](#order)
- [Process Payment](#payment)
- [Complete a payment (For remote gateways)](#complete)

<a name="introduction"></a>
## Introduction

The checkout process allows you to turn a users cart into an order, passing in billing and shipping [addresses](address), a [customer](customer), a [shipping](shipping) method and a [payment](payment) gateway. From there you can then process a payment for the order by passing through their credit card details or redirecting to an external gateway.

<a name="options"></a>
## Cart Options

Returns, Contents, Pricing, Addresses, Shipping & Payment options.

``` php
$cart = Cart::Checkout();
```

#### Asynchronous
``` js
moltin.Cart.Checkout(function(cart) {
    console.log(cart);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var cart = moltin.Cart.Checkout();

if ( cart.status === true ) {
    console.log(cart.result);
} else {
    // Not found...
}
```

<a name="order"></a>
## Create Order from Cart

Passes the cart and options to the checkout, creates the order and returns it.

``` php
$order = Cart::Order([
    'customer' => '<CUSTOMER ID>',
    'shipping' => '<SHIPPING SLUG>',
    'gateway'  => '<GATEWAY SLUG>',
    'bill_to'  => '<ID, ARRAY, OR "ship_to">',
    'ship_to'  => '<ID, ARRAY, OR "bill_to">'
]);
```

#### Asynchronous
``` js
moltin.Cart.Order({
    customer: '<CUSTOMER ID>',
    shipping: '<SHIPPING SLUG>',
    gateway:  '<GATEWAY SLUG>',
    bill_to:  '<ID, ARRAY, OR "ship_to">',
    ship_to:  '<ID, ARRAY, OR "bill_to">'
}, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Cart.Order({
    customer: '<CUSTOMER ID>',
    shipping: '<SHIPPING SLUG>',
    gateway:  '<GATEWAY SLUG>',
    bill_to:  '<ID, ARRAY, OR "ship_to">',
    ship_to:  '<ID, ARRAY, OR "bill_to">'
});

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

<a name="payment"></a>
## Process Payment

Completes the checkout, processes payment and updates the order.

``` php
$result = Checkout::Payment('<METHOD>', '<ORDER ID>', [
    'data' => [
        'number'       => '<CARD NUMBER>',
        'expiry_month' => '<CARD EXPIRY MONTH>',
        'expiry_year'  => '<CARD EXPIRY YEAR>',
        'cvv'          => '<CARD CVV NUMBER>'
    ]
]);
```

#### Asynchronous
``` js
moltin.Checkout.Payment('<METHOD>', '<ORDER ID>', {
    data: {
        number:       '<CARD NUMBER>',
        expiry_month: '<CARD EXPIRY MONTH>',
        expiry_year:  '<CARD EXPIRY YEAR>',
        cvv:          '<CARD CVV NUMBER>'
    }
}, function(result) {
    console.log(result);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Checkout.Payment('<METHOD>', '<ORDER ID>', {
    data: {
        number:       '<CARD NUMBER>',
        expiry_month: '<CARD EXPIRY MONTH>',
        expiry_year:  '<CARD EXPIRY YEAR>',
        cvv:          '<CARD CVV NUMBER>'
    }
});

if ( result.status === true ) {
    console.log(result.result);
} else {
    // Something went wrong...
}
```

> **Note:** The data required varies by gateway, the above example is using Stripe.

### Available Payment Methods

Method | Description
------ | -----------
authorize | Authorize an amount on the customers card, doesn't take payment
complete_authorize | Handle return from off-site gateways after authorization
capture | Capture an amount you have previously authorized
purchase | Authorize and immediately capture an amount on the customers card
complete_purchase | Handle return from off-site gateways after purchase
refund | Refund an already processed transaction
void | Generally can only be called up to 24 hours after submitting a transaction

<a name="complete"></a>
## Complete a payment for remote gateways

Some gateways require you to redirect to an external URL (PayPal, SagePay, etc..). For this case the payment flow is shifted outside of the API and you will need to update any payments, orders and transactions manually.

You can call this endpoint once you've verified the payment is or is not complete.

``` php
$result = Checkout::Complete('<ORDER ID>', [
    'data' => [
        'order_status'           => '<PAYMENT STATUS>',
        'transaction_success'    => '<TRANSACTION SUCCESS>',
        'transaction_reference'  => '<TRANSACTION REFERENCE>'
    ]
]);
```

#### Asynchronous
``` js
moltin.Checkout.Complete('<ORDER ID>', {
    data: {
        'order_status':          '<PAYMENT STATUS>',
        'transaction_success':   '<TRANSACTION SUCCESS>',
        'transaction_reference': '<TRANSACTION REFERENCE>'
    }
}, function(result) {
    console.log(result);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Checkout.Complete('<ORDER ID>', {
    data: {
        'order_status':          '<PAYMENT STATUS>',
        'transaction_success':   '<TRANSACTION SUCCESS>',
        'transaction_reference': '<TRANSACTION REFERENCE>'
    }
});

if ( result.status === true ) {
    console.log(result.result);
} else {
    // Something went wrong...
}

Method | Description
------ | -----------
order_status | "paid", "dispatched", "processing", "refunded", "cancelled", "failed", "declined", "mismatch" | The status of the order
transaction_success | 1, 0 | The transaction success
transaction_reference | A reference to the transaction from the payment gateway





