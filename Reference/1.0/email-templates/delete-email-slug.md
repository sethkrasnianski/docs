<!--
@title Delete email template by slug
@author Moltin Ltd
@description Deletes an email template with a given slug

@sidebar 1
@family Email Templates
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes an email template with the specified slug.

#### Resource URL
DELETE [{{ api_url }}email/:slug]({{ api_url }}email/:slug)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "message": "Email template deleted successfully"
}
```


#### Example Invalid Slug Response
``` json
{
  "status": false,
  "error": "Email template not found"
}
```
<!--/code-->