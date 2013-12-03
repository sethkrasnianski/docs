<!--
@title GET shipping/:id
@author Moltin Ltd
@description Returns a shipping method of the given ID

@sidebar 1
@family Shipping
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a shipping method based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ url }}shipping/:id]({{ url }}shipping/:id)


#### Paramaters
None required

<!--code-->
#### Example Successful Response    {#success}
``` json
{
  "status": true,
  "result": {
    "id": "154",
    "title": "Free Shipping",
    "slug": "free",
    "company": "FedEx",
    "status": {
      "key": "1",
      "value": "Live"
    },
    "price": "0",
    "price_min": "10.00",
    "price_max": "100.00",
    "weight_min": "10.00",
    "weight_max": "100.00",
    "description": "Free shipping on orders between £10 and £100",
    "tax_band": {
      "id": 1,
      "title": "Default",
      "description": null,
      "rate": "20.00"
    }
  }
}
```


### Example Failed Response  {#error}
``` json
{
    "status": false,
    "error": "No shipping method found"
}
```
<!--/code-->