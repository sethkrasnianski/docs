This call deletes a webhook with the specified id.

#### Resource URL
DELETE [{{ api_url }}webhook/:id]({{ api_url }}webhook/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Webhook removed successfully"
}
```


#### Example Invalid ID Response
``` json
{
  "status": false,
  "error": "Webhook not found"
}
```
<!--/code-->