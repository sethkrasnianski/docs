<!--
@title GET categories
@author Moltin Ltd
@description Gets an array of categories

@sidebar 1
@family Categories
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a range of categories based on a given set of paramaters. All choices and relaionships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL	{#resource}
GET [{{ url }}categories]({{ url }}categories)


#### Paramaters	{#paramaters}
Key | Type | Description
--- | ---- | -----------
limit*optional* | Integer | The number of categories to return, defaults to all
offset*optional* | Integer | The first category to be shown, used for pagination


#### Example Successful Response	{#success}
``` json
TBA
```


### Example Empty Response	{#error}
``` json
TBA
```
