<!--
@title PUT taxes
@author Moltin Ltd
@description Mass updates currency tax rates
@order 11.2

@sidebar 1
@family Tax
@rate No
@auth Yes
@format JSON
@http PUT
@version beta
-->

This endpoint mass updates the currency tax rates.


#### Resource URL
PUT [{{ url }}taxes]({{ url }}taxes)


#### Paramaters
Key | Type | Description
--- | ---- | -----------
assignments[:currencyId][:taxId] | Decimal | The tax rate (percentage) for this tax band in this currency

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Tax rates have been updated successfully"
}
```


### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "'99' is not a valid tax band"
  ]
}
```
<!--/code-->