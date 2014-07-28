<!--
@title Delete currency by ID
@author Moltin Ltd
@description Deletes a currency with a given ID

@sidebar 1
@family Currency
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a currency with the specified id.

#### Resource URL
DELETE [{{ url }}currency/:id]({{ url }}currency/:id)


#### parameters
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