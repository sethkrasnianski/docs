Returns a brand based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}brand/:id]({{ api_url }}brand/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": {
    "id": "98",
    "title": "Example Brand",
    "slug": "example-brand",
    "status":
    {
      "key": "1",
      "value": "Live"
    },
    "description": "Example brand description"
  }
}
```


### Example Empty Response
``` json
{
    "status": false,
    "error": "No brand found"
}
```
<!--/code-->