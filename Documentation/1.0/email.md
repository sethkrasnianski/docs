# Email Templates

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Email](#single)
- [Multiple Emails](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)

<a name="introduction"></a>
## Introduction

Email are part of a system to integrate the Moltin API into external systems with ease.

Email can be used to send back specific data to external endpoints based around actions on th API.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Name | name | String | No | No | The name of the email.
Subject | subject | String | Yes | No | The subject of the email
Url | url | String | Yes | Yes | The URL to the email.
Secret | secret | String | No | No | A secret key that you can match against when your URL is called.
Content Type | content_type | String | Yes | No | JSON or x-form-urlencoded? json or form.
Enabled | enabled | Boolean | Yes | No | Enabled or Disabled? 1 or 0.

<a name="object"></a>
## Object

Below is an example of a email object, showing the data structure to expect.

	{
	    "name": "Order Paid",
	    "subject": "Your payment has been processed",
	    "slug": "order_paid",
	    "url": "http://molt.in/templates/order_paid.html",
	    "content_type": {
	        "value": "application/x-www-form-urlencoded",
	        "data": {
	            "key": "form",
	            "value": "application/x-www-form-urlencoded"
	        }
	    },
	    "secret": null,
	    "enabled": {
	        "value": "No",
	        "data": {
	            "key": 0,
	            "value": "No"
	        }
	    },
	    "locked": {
	        "value": "Yes",
	        "data": {
	            "key": 1,
	            "value": "Yes"
	        }
	    }
	}

<a name="single"></a>
## Single Email

``` php
$email = Email::Get('<SLUG>');
```

<a name="multiple"></a>
## Multiple Emails

``` php
$email = Email::Listing(['status' => '1']);
```

<a name="create"></a>
## Create

``` php
$email = Email::Create([
    'name'         => 'Order Complete',
    'subject'      => 'Your order from Test Store',
    'url'          => 'http://example.com/emails/order-complete.html',
    'secret'       => '',
    'content_type' => 'json',
    'enabled'      => 1
]);
```

<a name="update"></a>
## Update

``` php
$email = Email::Edit('<SLUG>', [
    'url'    => 'http://example.com/emails/order-complete.php',
    'secret' => '4234n2i3n4234',
]);
```

<a name="delete"></a>
## Delete

``` php
Email::Delete('<SLUG>');
```
