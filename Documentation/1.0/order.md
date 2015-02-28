# Orders

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Order](#single)
- [Multiple Order](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)

<a name="introduction"></a>
## Introduction

Orders are [flows](flows) based data structures.

Orders has a basic data structure containing only the most necessary information; however this can be extended via [flows](flows). This additional data allows you to customise order to meet the needs of your project, and will automatically be added to your [forge](forge) instance for ease of use.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Customer   |       customer |         Integer |    No |           No | The customer ID.
Gateway    |       gateway |          String |    No |           No | The payment gateway slug.
Status |       status |       String |    Yes |           No | The order status, paid, unpaid, dispatched, processing, cancelled, failed, declined, mismatch, refunded, partial_refund.
Sub Total |        subtotal |        Decimal |   Yes |           No | The order subtotal (before shipping and tax).
Shipping Price |         shipping_price |         Decimal |   No |           No | The shipping price of the order.
Total | total |     Decimal |   Yes  |           No | The order total (after tax and shipping).
Currency | currency |     Integer |   Yes  |           No | The currency ID.
Currency Code | currency_code |   String |   Yes  |           No | The currency code.
Exchange Rate | exchange_rate |   Decimal |   Yes  |           No | The currency exchange rate.
Ship To | ship_to |     Integer  |   yes  |           No | The customers shipping address.
Bill To | bill_to |           Integer |   Yes |           No | The customers billing address.
Shipping | shipping | Integer | No | No | The ID of the shipping method

> **Note:** Due to order being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of a order object, showing the data structure to expect.

    {
        "id": "994",
        "product":
        {
            "value": "Espresso Cup - Small Red",
            "data": <a href="product#object">[PRODUCT OBJECT]</a>
        },
        "sku": "PRD_H0003_SMRE",
        "title": "Espresso Cup - Small Red",
        "price": "14.99",
        "quantity": 1,
        "tax_rate": "20.00",
        "tax_band":
        {
            "value": "Default",
            "data": <a href="tax#object">[TAX OBJECT]</a>
        },
        "created_at": "2014-05-30 12:44:41",
        "updated_at": "2014-05-30 12:44:41"
    }

<a name="single"></a>
## Single Order

### Via Id

``` php
$order = Order::Get('<ID>');
```

#### Asynchronous
``` js
moltin.Order.Get('<ID>', function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Order.Get('<ID>');

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

### Via Criteria

``` php
$order = Order::Find(['status' => '1']);
```

#### Asynchronous
``` js
moltin.Order.Find({status: '1'}, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Order.Find({status: '1'});

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

<a name="multiple"></a>
## Multiple Order

``` php
$order = Order::Listing();
```

#### Asynchronous
``` js
moltin.Order.List(null, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Order.List();

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

<a name="create"></a>
## Create

``` php
$order = Order::Create([

]);
```

#### Asynchronous
``` js
moltin.Order.Create({
    
}, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Order.Create({
    
});

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

<a name="update"></a>
## Update

``` php
$order = Order::Edit(<ID>, [

]);
```

#### Asynchronous
``` js
moltin.Order.Update('<ID>', {
    
}, function(order) {
    console.log(order);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var order = moltin.Order.Update('<ID>', {
    
});

if ( order.status === true ) {
    console.log(order.result);
} else {
    // Something went wrong...
}
```

<a name="delete"></a>
## Delete

``` php
Order::Delete('<ID>');
```

#### Asynchronous
``` js
moltin.Order.Delete('<ID>', function() {
    // Success
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var result = moltin.Order.Delete('<ID>');

if ( result.status === true ) {
    // Success
} else {
    // Something went wrong...
}
```