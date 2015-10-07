# Promotions

> **Note:** Available now in v1 of the API, Forge implementation is on the way.

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Apply](#apply)
- [Remove](#remove)
- [Promotion Types](#type)
- [Rules](#rule)
- [Single Promotion](#single)
- [Multiple Promotions](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)
- [Fields](#field)

<a name="introduction"></a>
## Introduction

Promotions allow you to create powerful discount rules for your carts that are either applied automatically or via the use of a voucher code. These promotions can be totally customised using the powerful rule builder to limit rules to specific products, groups, customers, cart values and more.

> **Note:** While this document goes into great length about how to create and structure discount rules, please consider using the GUI in Forge (when it's implemented).

<a name="params"></a>
## Parameters

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Title | title | String | Yes | No | -
Description | description | Text | No | No | -
Discount Code | discount_code | String | No | Yes | The voucher code to be used (if applicable).
From Date | from | Date | Yes | No | Start date of the promotion.
To Date | to | Date | Yes | No | End date of the promotion
Maximum uses | max_uses | Integer | No | No | Maximum number of uses across the entire store.
Uses per customer | customer_uses | Integer | No | No | Maximum number of uses per customer.
Customer Group | customer_group | Multiple | No | No | Relates to [customer](customer).
Status | status | Choice | Yes | No | Choices available are 0 (Disabled), 1 (Enabled).
Terminate processing further promotions? | terminating | Choice | Yes | No | Stop processing further discounts after match? Choices available are 0 (No), 1 (Yes).
Persist if terminated? | persistent | Choice | Yes | No | Persist after termination? Choices available are 0 (No), 1 (Yes).
Action | action | Choice | Yes | No | Choices available are [free_ship](#type), [buy_x_get_y_free](#type), [discount_by_fixed](#type), [discount_by_percent](#type), [discount_to_fixed](#type), [discount_subtotal_fixed](#type), [discount_subtotal_percent](#type).
Priority | priority | Integer | No | No | Order to run promotions in.
Discount Amount | amount | Decimal | Yes | No | Decimal limited to 2 places.
Maximum Discount Quantity | max_quantity | Decimal | No | No | Maximum discount to apply. Decimal limited to 2 places.
Discount Trigger Quantity | trigger_quantity | Integer | No | No | What quantity should this be triggered on?
Apply discount to shipping | apply_to_shipping | Choice | Yes | No | Choices available are 0 (No), 1 (Yes).
Shipping methods | shipping_methods | Multiple | No | No | Relates to [shipping](shipping).
Match items | match_items | JSON | No | No | JSON object to specify which products this should apply to.
Match rules | match_rules | JSON | No | No | JSON object to specify the conditions in which this promotion should apply.

> **Note:** Due to promotions being flows-based this may not be an accurate representation of your stores parameters. If you have added any additional fields that are required and you only pass in what is shown here you may get errors.

<a name="object"></a>
## Object

Below is an example of an promotion object, showing the data structure to expect.

    {
        "id": "68118201195561607",
        "order": null,
        "created_at": "2015-04-04 23:38:42",
        "updated_at": "2015-04-05 01:42:36",
        "from": "2015-01-01",
        "to": "2015-12-31",
        "max_uses": 1000,
        "customer_uses": 0,
        "customer_group": null,
        "status": {
            "value": "Enabled",
            "data": {
                "key": "1",
                "value": "Enabled"
            }
        },
        "terminating": {
            "value": "No",
            "data": {
                "key": "0",
                "value": "No"
            }
        },
        "persistent": {
            "value": "No",
            "data": {
                "key": "0",
                "value": "No"
            }
        },
        "action": {
            "value": "Buy x get y free",
            "data": {
                "key": "buy_x_get_y_free",
                "value": "Buy x get y free"
            }
        },
        "priority": 0,
        "amount": 1,
        "max_quantity": 0,
        "trigger_quantity": 4,
        "apply_to_shipping": {
            "value": "No",
            "data": {
                "key": "0",
                "value": "No"
            }
        },
        "shipping_methods": null,
        "description": "Test buy 4 get 1 free",
        "title": "TEST (BFGOF)",
        "discount_code": "",
        "match_rules": null,
        "match_items": {
            "type": "group",
            "operator": "",
            "match": "",
            "against": "",
            "children": [
                {
                    "type": "cart_item",
                    "operator": "=",
                    "match_on": "any",
                    "match": "sku",
                    "against": "TEST01"
                }
            ],
            "match_on": "any"
        }
    }

<a name="apply"></a>
## Apply

``` php
$cart = Cart::Discount('<CODE>');
```

#### Asynchronous
``` js
moltin.Cart.Discount('<CODE>', function(cart) {
    console.log(cart);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var cart = moltin.Cart.Discount('<CODE>');

if ( cart.status === true ) {
    console.log(cart.result);
} else {
    // Something went wrong...
}
```

<a name="remove"></a>
## Remove

``` php
$cart = Cart::Discount();
```

#### Asynchronous
``` js
moltin.Cart.Discount(false, function(cart) {
    console.log(cart);
}, function(error) {
    // Something went wrong...
});
```

#### Synchronous
``` js
var cart = moltin.Cart.Discount();

if ( cart.status === true ) {
    console.log(cart.result);
} else {
    // Something went wrong...
}
```

<a name="type"></a>
## Promotion Types

Within promotions there are a number of types that you can apply, either automatically or with a voucher code. There are seven available types:

1. **Buy X get Y free** - Buy X quantity (controlled by ```trigger_quantity```), Y (```amount```) are free.
2. **Discount by fixed** - Removes X value (```amount```) from each matching item.
3. **Discount by percent** - Removes X percent (```amount```) from each matching item.
4. **Discount to fixed** - Makes each match item X value (```amount```).
5. **Discount subtotal by fixed** - Remove X value (```amount```) from the cart subtotal.
6. **Discount subtotal by percent** - Remove X percent (```amount```) from the cart subtotal.
7. **Free shipping** - Makes shipping free.

<a name="rule"></a>
## Rules

Promotion rules are JSON objects designed to allow you to write advanced matches and come in two variations, ```match_rules``` and ```match_items```. ```match_rules``` allow you to limit a promotion to cart attributes like total value, number of items, etc or customer attributes like previous sales or group. ```match_items``` are similar and allow you match a promotion on a products attributes, like SKU, group, category and more.

> **Note:** All rules can be nested and used in combination to create more advanced promotions.

### All or Any?

As the top level of each ruleset, there is an empty condition which declares that the rule can be applied if all or any of the children rules match. This rule looks like the following:

	{
		"type":     "group",
		"operator": "",
		"match":    "",
		"against":  "",
		"children": [],
		"match_on": "any"
	}

### Basic Example

In this next example you'll see how to do a ```match_items``` condition which will apply the promotion only to items with a specific SKU. Any product field can be supplied instead or as well as it.

	{
		"type":     "group",
		"operator": "",
		"match":    "",
		"against":  "",
		"children": [
			{
				"type":     "cart_item",
				"operator": "=",
				"match_on": "any",
				"match":    "sku",
                "against":  "PRD_H0001"
            }
        ],
		"match_on": "any"
	}

To break this down further, the rule simply states:

1. Apply promotion if we match any of the following rules:
2. Match any cart item by sku against PRD_H0001

### Advanced Example

Here we'll create a ```match_rules``` condition to check if our customer is a staff member and their cart is worth over $100:

	{
		"type":     "group",
		"operator": "",
		"match":    "",
		"against":  "",
		"children": [
        	{
        		"type":     "customer",
        		"operator": "=",
        		"match":    "group",
        		"against":  "staff"
        	},
        	{
        		"type":     "cart_attribute",
        		"operator": ">",
        		"match":    "price",
        		"against":  100
        	}
        ],
		"match_on": "all"
	}

Again to break this down:

1. Apply promotion if we match all of the following rules:
2. Match a customer in the group staff
3. Match a cart worth over $100

### Rule Types

With each rule you must define a type, these allow the rule engine to know what it's dealing with and what it can match on. The available types are:

1. **group** - allows for grouping of rules for more complex matching
2. **cart_attribute** - matches on cart attributes, like value, number of items, etc.
3. **cart_item** - matches on cart item properties, like price, quantity, sku, etc.
4. **customer** - matches on a customers group, history and more.

### Operators

When defining rules you can use any of the following operators:

	=, !=, >=, <=, >, <, in and !in

<a name="single"></a>
## Single Promotion

``` php
$promotion = Promotion::Get('<ID>');
```

<a name="multiple"></a>
## Multiple Promotions

``` php
$promotions = Promotion::Listing(['code' => 'example']);
```

<a name="create"></a>
## Create

``` php
$promotion = Promotion::Create([
	'title'             => 'Test Promotion',
	'description'       => 'My first promotion.',
	'discount_code'     => 'TEST20',
	'from'              => '2015-04-01',
	'to'                => '2015-04-31',
	'max_uses'          => 100,
	'customer_uses'     => 1,
	'status'            => 1,
	'terminating'       => 0,
	'persist'           => 0,
	'action'            => 'discount_subtotal_fixed',
	'priority'          => 1,
	'amount'            => 20,
	'apply_to_shipping' => 0,
	'match_rules'       => null,
	'match_items'       => null
]);
```

<a name="update"></a>
## Update

``` php
$promotion = Promotion::Edit('<ID>', [
    'max_uses'      => 1000,
    'discount_code' => 'TEST50',
    'amount'        => 50
]);
```

<a name="delete"></a>
## Delete

``` php
Promotion::Delete('<ID>');
```

<a name="field"></a>
## Fields

### Create

#### Field Data
``` php
$fields = Promotion::Fields();
```

#### Pre-built Form
``` php
$fields = Promotion::Fields(null, true);

echo '<form method="promotion/create" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Create</button>';
echo '</form>';
```

### Update

#### Field Data
``` php
$fields = Promotion::Fields('<ID>');
```

#### Pre-built Form
``` php
$fields = Promotion::Fields('<ID>', true);

echo '<form method="promotion/edit/<ID>" action="post">';
foreach ( $fields as $field ) {
    echo '<label for="'.$field['slug'].'">'.$field['title'].'</label>';
    echo $field['input'];
}
echo '<button type="submit">Edit</button>';
echo '</form>';
```
