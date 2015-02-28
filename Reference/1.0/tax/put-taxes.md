This endpoint mass updates the currency tax rates.


#### Resource URL
PUT [{{ api_url }}taxes]({{ api_url }}taxes)


#### Parameters
Key | Type | Description
--- | ---- | -----------
fields[:currencyId][:taxId] | Decimal | The tax rate (percentage) for this tax band in this currency

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Tax rates have been updated successfully"
}
```


#### Example Failed Response
``` json
{
  "status": false,
  "errors": [
    "'99' is not a valid tax band"
  ]
}
```
<!--/code-->