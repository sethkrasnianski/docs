This call deletes a currency with the specified id.

#### Resource URL
DELETE [{{ api_url }}currencies/:id]({{ api_url }}currencies/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Currency deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
  "status": false,
  "error": "Currency not found"
}
```
<!--/code-->