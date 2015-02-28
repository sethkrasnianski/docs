# Webhooks

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Single Webhook](#single)
- [Multiple Webhooks](#multiple)
- [Create](#create)
- [Update](#update)
- [Delete](#delete)

<a name="introduction"></a>
## Introduction

Webhooks are callbacks to an external location you define in order to recieve information on any create, update or delete action performed in the API. This allows you to listen for events rather than having to poll for changes to your store, allowing integrations with accountancy software, channel partners and more.

> **Note:** Webhooks will be tried 3 times over a 30 minute period, if no 200 response is recieved after those attempts, the data will be logged and made available under the forge dashboard.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this flow, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Name | name | String | No | No | The name of the webhook.
Url | url | String | Yes | Yes | The URL to the webhook.
Secret | secret | String | No | No | A secret key that you can match against.
Content Type | content_type | String | Yes | No | JSON or x-form-urlencoded? json or form.
Create | create | Boolean | Yes | No | Enable on create events? 1 or 0.
Update | update | Boolean | Yes | No | Enable on update events? 1 or 0.
Delete | delete | Boolean | Yes | No | Enable on delete events? 1 or 0.
Enabled | enabled | Boolean | Yes | No | Enabled or Disabled? 1 or 0.

<a name="object"></a>
## Object

Below is an example of a webhook object, showing the data structure to expect.

	{
	    "id": "7aa8ad0d-69ea-419a-a4c3-fe8ee69fc2b8",
	    "url": "http://demo.molt.in/test.php",
	    "content_type": {
	        "value": "application/x-www-form-urlencoded",
	        "data": {
	            "key": "form",
	            "value": "application/x-www-form-urlencoded"
	        }
	    },
	    "secret": null,
	    "create": {
	        "value": "Yes",
	        "data": {
	            "key": 1,
	            "value": "Yes"
	        }
	    },
	    "update": {
	        "value": "Yes",
	        "data": {
	            "key": 1,
	            "value": "Yes"
	        }
	    },
	    "delete": {
	        "value": "Yes",
	        "data": {
	            "key": 1,
	            "value": "Yes"
	        }
	    },
	    "enabled": {
	        "value": "Yes",
	        "data": {
	            "key": 1,
	            "value": "Yes"
	        }
	    }
	}

<a name="single"></a>
## Single Webhook

### Via Id

``` php
$webhook = Webhook::Get('<ID>');
```

### Via Criteria

``` php
$webhook = Webhook::Find(['title' => 'Test Webhook']);
```

<a name="multiple"></a>
## Multiple Webhooks

``` php
$webhook = Webhook::Listing(['status' => '1']);
```

<a name="create"></a>
## Create

``` php
$webhook = Webhook::Create([
    'name'         => 'Test Webhook',
    'subject'      => 'Just testing...',
    'url'          => 'http://example.com/test.php',
    'secret'       => '2130402hdjwef3ee',
    'content_type' => 'json',
    'create'       => 1,
    'update'       => 0,
    'delete'       => 0,
    'enabled'      => 1
]);
```

<a name="update"></a>
## Update

``` php
$webhook = Webhook::Edit('<ID>', [
    'url'    => 'http://example.com/test2.php',
    'secret' => 'n123in123i12n31',
    'update' => 1
]);
```

<a name="delete"></a>
## Delete

``` php
Webhook::Delete('<ID>');
```
