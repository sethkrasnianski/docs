<!--
@title GET product/:id/assignments
@author Moltin Ltd
@description Gets the given products flow data and field assignments

@sidebar 1
@family Product
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
This call returns the data required to build a dynamic flows form based on the product edit requirements. It provides all options available for the choice fields as well as those featured in relationships (eg, Categories). It also provides information of field requirements, default values, etc.

Unlike /products/assignments this adds the current products data to the array to allow for prepopulation of fields.

#### Resource URL	{#resource}
[{{ url }}product/:id/assignments]({{ url }}product/:id/assignments)


#### Paramaters	{#paramaters}
N/A


#### Example Successful Response	{#success}
``` json
TBA
```

#### Example Invalid Response	{#error}
``` json
TBA
```