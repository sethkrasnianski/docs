This call deletes a category with a given ID or a set of categories in a comma-seperated list of IDs. Once a category has been deleted all products in that category will be removed and possibly unavailable.

#### Resource URL
DELETE [{{ api_url }}categories/:id]({{ api_url }}categories/:id)

<!--code-->
``` json
{
    "status": true,
    "message": "Category removed successfully"
}
```
<!--/code-->
