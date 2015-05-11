This call deletes a language with the specified slug.

#### Resource URL
DELETE [{{ api_url }}languages/:slug]({{ api_url }}languages/:slug)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Language deleted successfully"
}
```


#### Example Invalid Slug Response
``` json
{
  "status": false,
  "error": "Language not found"
}
```
<!--/code-->