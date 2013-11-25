<!--
@title DELETE tax/:id
@author Moltin Ltd
@description Deletes a tax band with a given ID

@sidebar 1
@family Tax
@rate No
@auth Yes
@format JSON
@http DELETE
@version beta
-->
This call deletes a tax band with a given ID.

#### Resource URL
DELETE [{{ url }}tax/:id({{ url }}tax/:id)


#### Paramaters
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