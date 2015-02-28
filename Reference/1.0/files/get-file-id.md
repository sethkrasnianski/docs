<!--
@title Get file by ID
@author Moltin Ltd
@description Returns a file of the given ID

@sidebar 1
@family Files
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->

Returns a file based on a given ID. Any relational objects will also be returned as either key, values or for multiple-relational items an array.


#### Resource URL
[{{ api_url }}file/:id]({{ api_url }}file/:id)


#### Parameters
None required

<!--code-->
#### Example Successful Response
``` json
{
    "status": true,
    "result": {
        "id": 1,
        "url": {
            "http": "http://commercecdn.com/1/phpAaYpko",
            "https": "https://commercecdn.com/1/phpAaYpko"
        },
        "segments": {
            "domain": "commercecdn.com/",
            "suffix": "1/phpAaYpko"
        }
    }
}
```


#### Example Empty Response
``` json
{
    "status": false,
    "error": "No file found"
}
```
<!--/code-->