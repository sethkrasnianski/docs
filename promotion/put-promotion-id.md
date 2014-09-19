<!--
@title Update a promotion
@author Moltin Ltd
@description Updates a promotion with the given ID
@order 2.2

@sidebar 1
@family Promotion
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->
This call edits a promotion with a given ID. There are no minumum required parameters and only those differing from current values will be updated, as such you can pass all or one of the fields and there will be no difference.


#### Resource URL
PUT [{{ url }}promotion/:id]({{ url }}promotion/:id)


#### Parameters
Key | Type | Description
--- | ---- | -----------
title*optional* | String | The Title of the promotion, must be unique
slug*optional* | String | The Slug/URI of the promotion, must be unique
parent*optional* | Integer | The Parent promotion ID of the promotion, can be null
status*optional* | Choice (1 or 0) | Is the product Live or a Draft
description*optional* | String | The Description of the product

<!--code-->
#### Example Successful Response
``` json

```


### Example Failed Response
``` json

```
<!--/code-->