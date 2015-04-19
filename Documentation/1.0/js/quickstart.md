# Quickstart

- [Install the JS SDK](#step-1)
	- [Include SDK script](#include)
	- [or Download & include](#download)
	- [Authenticate](#auth)
- [A simple checkout flow](#step-2)
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

``` html
<script src="https://js.moltin.com/v1"></script>
```

<a name="download"></a>
### Download & include SDK script

If you want to host the JavaScript SDK yourself instead, you can download it and include the script locally.

``` html
<script src="/path/to/local/moltin.min.js"></script>
```

[Download the JS SDK](https://github.com/moltin/js-sdk)

<a name="auth"></a>
### Authenticate

initialize the Moltin SDK:

	var moltin = new Moltin({publicId: '{{ client_id }}'});
	moltin.Authenticate(function() {
	  
	  // Add further calls here

	});

<a name="step-2"></a>
## A simple checkout flow

<a name="product"></a>
### Get a product

Now that we've authenticated with the Moltin API lets get one of our sample products.

	var product = moltin.product.find({slug: 'decorative-hedgehogs'});

The product variable contains this products data such as price, descriptions and images. A good place to display this data is on a product or listing page.

<a name="product-cart"></a>
### Add product to cart

Using a product ID we can insert a quantity of this product into the cart with one simple request. The first parameter passed is the product ID, the second the quantity to be added to the cart. The last parameter is product variation data, but for this example we'll leave it as null

	var item = moltin.cart.insert(product.id, 1, null);

item is an object containing the individual cart item data e.g. title, quantity, price. A good example to integrate this would be to add a simple button or form to the product page that posts the product ID and quantity to this endpoint.

<a name="cart"></a>
### Get cart contents

Now that there is atleast one product in the cart lets get the full cart contents.

	var cart = moltin.cart.contents();

cart is an object containing all of the cart items and cart totals. A good place to show this data would be on the cart or orders page, or even a widget in the header of your website.

<a name="cart-order"></a>
### Convert cart to order

When the customer is ready to checkout we need to convert the cart to an order. This call lets you define the payment gateway and conditional order parameters such as customer, billing and shipping addresses.

	var order = moltin.Cart.Complete({gateway: 'dummy'});

This call will return an object containing data for the new order created.

<a name="payment"></a>
### Process payment

Once we've converted a cart into an order we're now ready to process a payment. In this example we've used the dummy gateway so we just need to provide some card details. The data you need to provide in this step depends on your chosen gateway.

	var checkout = moltin.Checkout.Payment('purchase', order.id, {
		data {
	  		number:       '4242424242424242',
	  		expiry_month: '02',
	  		expiry_year:  '2017',
	  		cvv:          '123'
	  	}
	});

Congratulations, if you made it this far you've implemented a simple step by step javascript only checkout!

<a name="step-3"></a>
## Jump start your own project

We've created a number of example projects that let you get started in minutes.

### JavaScript Storefront

Grab our example JavaScript storefront and see all of this working together in a JavaScript application! Customise or use as inpiration for your own projects.

[View on Github](https://github.com/moltin/js-demo)

### Starter Project

If you want something a little more simple we've put together a basic starter project for you which includes the JS SDK and authentication call.

[View on Github](https://github.com/moltin/js-example)
