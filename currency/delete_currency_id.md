<!--
@title DELETE currency/:id
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

#### Resource URL	{#resource}
DELETE [{{ url }}currency/:id]({{ url }}currency/:id)


#### Paramaters	{#paramaters}
None required


#### Example Successful Response	{#success}
``` json
{
  "status": true,
  "message": "Currency deleted successfully"
}
```


#### Example Invalid ID Response	{#error}
``` json
{
  "status": false,
  "error": "Currency not found"
}
```
