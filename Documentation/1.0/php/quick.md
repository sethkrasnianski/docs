# Quickstart

- [Install the PHP SDK](#step-1)
	- [Get Composer](#composer)
	- [Install the SDK](#install)
	- [Authenticate](#auth)
- [A simple checkout flow](#step-3)
	- [Get a product](#product)
	- [Add product to cart](#product-cart)
	- [Get cart contents](#cart)
	- [Convert cart to order](#cart-order)
	- [Process payment](#payment)
- [Jump start your own project](#step-3)

<a name="step-1"></a>
## Install the PHP SDK

<a name="composer"></a>
### Get Composer

The recommended way to install the SDK is to use Composer to manage installation and creation of the autoload script.

[Download Composer](https://getcomposer.org/download/)

<a name="install"></a>
### Install the SDK

Add to, or create, composer.json in your project folder:

	{
		"require" : {
		  "moltin/php-sdk" : "dev-version1"
		}
	}

Execute composer with the install parameter (i.e. composer install). This will download the Moltin PHP SDK and create autoload.php in the vendor directory.

<a name="auth"></a>
### Authenticate

Require the autoload.php file, and initialize Moltin:

	require 'vendor/autoload.php';

	use Moltin\SDK\Facade\Moltin as Moltin;

	Moltin::Authenticate('ClientCredentials', [
	    'client_id'     => '<CLIENT_ID>',
	    'client_secret' => '<CLIENT_SECRET>'
	]);

<a name="step-2"></a>
## A simple checkout flow

<a name="product"></a>
### Get a product

Now that we've authenticated with the Moltin API lets get one of our sample products.

	$product = \Product::Find(['slug' => 'decorative-hedgehogs']);

$product should contain an array of the products data. A good place to display this data is on a product or listing page.

<a name="product-cart"></a>
### Add product to cart

Using a product ID we can insert a quantity of this product into the cart with one simple request. The first parameter passed is the product ID, the second the quantity to be added to the cart.

	$item = \Cart::Insert($product['id'], 1);

$item should contain an array of the individual cart item data e.g. title, quantity, price. A good example to integrate this would be to add a simple button or form to the product page that posts the product ID and quantity to this endpoint.

<a name="cart"></a>
### Get cart contents

Now that there is atleast one product in the cart lets get the full cart contents.

	$cart = \Cart::Contents();

$cart should contain an array of all cart items and cart totals. A good place to show this data would be on the cart or orders page, or even a widget in the header of your website.

<a name="cart-order"></a>
### Convert cart to order

When the customer is ready to checkout we need to convert the cart to an order. This call lets you define the payment gateway and conditional order parameters such as customer, billing and shipping addresses.

	$order = \Cart::Order(['gateway' => 'dummy']);

This call will return an object containing data for the new order created.

<a name="payment"></a>
### Process payment

Once we've converted a cart into an order we're now ready to process a payment. In this example we've used the dummy gateway so we just need to provide some card details. The data you need to provide in this step depends on your chosen gateway.

	$checkout = \Checkout::Payment('purchase', $order['id'], [
	  'data' => [ 
	    'number'       => '4242424242424242',
	    'expiry_month' => '02',
	    'expiry_year'  => '2017',
	    'cvv'          => '123'
	  ]
	]);

Congratulations, if you made it this far you've implemented a simple step by step PHP checkout!

<a name="step-3"></a>
## Jump start your own project

Grab our example project and see all of this working together in a simple PHP application! Customise or use as inpiration for your own projects.

[View Project on Github](https://github.com/moltin/framework)
