<!--
@title GET products
@author Moltin Ltd
@description Gets a list product based on the given criteria

@sidebar 1
@family Products
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of products based on a given set of paramaters. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.

#### Resource URL
[{{ url }}products]({{ url }}products)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of products to return
offset*optional* | Integer | The first product to be shown, used for pagination
