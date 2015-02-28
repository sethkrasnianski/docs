This call deletes a tax band with a given ID.

#### Resource URL
DELETE [{{ api_url }}tax/:id]({{ api_url }}tax/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Tax band deleted successfully"
}
```


#### Example Invalid ID Response
``` json
{
  "status": false,
  "message": "No tax found"
}
```
<!--/code-->
