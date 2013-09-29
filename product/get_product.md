<!--
@title GET product
@author Moltin Ltd
@description Gets a product based on the given criteria

@sidebar 1
@family Product 
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a product based on a given set of key-value properties. One or more paramaters can be passed to the method but they must all match exactly and the best match will be returned.

While this call is similar to search it will only return a single product.


#### Resource URL
[{{ url }}product]({{ url }}product)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
id*optional* | Integer | Select by ID
sku*optional* | String | Select by SKU
title*optional* | String | Select by Title
slug*optional* | String | Select by Slug
price*optional* | Float | Select by Price
sale_price*optional* | Float | Select by Sale Price
status*optional* | Choice (1 or 0) | Select by Status
category*optional* | Integer | Select by Category ID
stock_level*optional* | Integer | Select by Stock Level
stock_status*optional* | Choice (0 to 6) | Select by Stock Status
