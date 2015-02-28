# Quickstart

- [Install the JS SDK](#step-1)
	- [Include SDK script](#include)
	- [or Download & include](#download)
	- [Authenticate](#auth)
- [A simple checkout flow](#step-3)
	- [Get a product](#product)
	- [Add product to cart](#product-cart)
	- [Get cart contents](#cart)
	- [Convert cart to order](#cart-order)
	- [Process payment](#payment)
- [Jump start your own project](#step-3)

<a name="step-1"></a>
## Install the JS SDK

<a name="include"></a>
### Include SDK script

The recommended way to install the SDK is to include our SDK using our CDN.

	<script src="https://js.moltin.com/moltin.min.js"></script>

<a name="download"></a>
### Download & include SDK script

If you want to host the JavaScript SDK yourself instead, you can download it and include the script locally.

	<script src="/path/to/local/moltin.min.js"></script>

[Download the JS SDK](https://github.com/moltin/js-sdk)

<a name="auth"></a>
### Authenticate

initialize the Moltin SDK:

	var moltin = new Moltin({publicId: '{{ client_id }}'});
	moltin.Authenticate(function() {
	  
	  // Add further calls here

	});

