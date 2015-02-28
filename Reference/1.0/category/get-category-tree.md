<!--
@title Get category tree
@author Moltin Ltd
@description Gets an array of categories
@order 2.5

@sidebar 1
@family Category
@rate No
@auth Yes
@format JSON
@http GET
@version beta
-->
Returns a full structured categories based on a given set of parameters. All choices and relationships will be converted to their appropriate data values to reduce the number of extra calls required.


#### Resource URL
GET [{{ api_url }}categories/tree]({{ api_url }}categories/tree)


#### Parameters
N/A

<!--code-->
#### Example Successful Response
``` json
{
  "status": true,
  "result": [
    {
      "id": 16,
      "parent": null,
      "title": "Accessories",
      "slug": "accessories",
      "status":
      {
          "value": "Live",
          "data":
          {
              "key": "1",
              "value": "Live"
          }
      },
      "description": "Shop for all your must have accessories!",
      "tax_band": null,
      "created_at": null,
      "updated_at": "2014-07-21 12:36:38",
      "images": [],
      "children":
      [
          {
              "id": 213,
              "parent":
              {
                  "value": "Accessories",
                  "data":
                  {
                      "id": 16,
                      "parent": null,
                      "title": "Accessories",
                      "slug": "accessories",
                      "status":
                      {
                          "value": "Live",
                          "data":
                          {
                              "key": "1",
                              "value": "Live"
                          }
                      },
                      "description": "Shop for all your must have accessories!",
                      "tax_band": null,
                      "created_at": null,
                      "updated_at": "2014-07-21 12:36:38"
                  }
              },
              "title": "Jewelry",
              "slug": "jewelry",
              "status":
              {
                  "value": "Live",
                  "data":
                  {
                      "key": "1",
                      "value": "Live"
                  }
              },
              "description": "Jewelry",
              "tax_band": null,
              "created_at": null,
              "updated_at": "2014-07-21 12:36:38",
              "images": [],
              "children":
              [
                  {
                      "id": 214,
                      "parent":
                      {
                          "value": "Jewelry",
                          "data":
                          {
                              "id": 213,
                              "parent":
                              {
                                  "value": "Accessories",
                                  "data":
                                  {
                                      "id": 16,
                                      "parent": null,
                                      "title": "Accessories",
                                      "slug": "accessories",
                                      "status":
                                      {
                                          "value": "Live",
                                          "data":
                                          {
                                              "key": "1",
                                              "value": "Live"
                                          }
                                      },
                                      "description": "Shop for all your must have accessories!",
                                      "tax_band": null,
                                      "created_at": null,
                                      "updated_at": "2014-07-21 12:36:38"
                                  }
                              },
                              "title": "Jewelry",
                              "slug": "jewelry",
                              "status":
                              {
                                  "value": "Live",
                                  "data":
                                  {
                                      "key": "1",
                                      "value": "Live"
                                  }
                              },
                              "description": "Jewelry",
                              "tax_band": null,
                              "created_at": null,
                              "updated_at": "2014-07-21 12:36:38"
                          }
                      },
                      "title": "Rings",
                      "slug": "rings",
                      "status":
                      {
                          "value": "Live",
                          "data":
                          {
                              "key": "1",
                              "value": "Live"
                          }
                      },
                      "description": "Rings",
                      "tax_band": null,
                      "created_at": null,
                      "updated_at": "2014-07-21 12:36:38",
                      "images": []
                  }
              ]
          },
          {
              "id": 215,
              "parent":
              {
                  "value": "Accessories",
                  "data":
                  {
                      "id": 16,
                      "parent": null,
                      "title": "Accessories",
                      "slug": "accessories",
                      "status":
                      {
                          "value": "Live",
                          "data":
                          {
                              "key": "1",
                              "value": "Live"
                          }
                      },
                      "description": "Shop for all your must have accessories!",
                      "tax_band": null,
                      "created_at": null,
                      "updated_at": "2014-07-21 12:36:38"
                  }
              },
              "title": "Belts",
              "slug": "belts",
              "status":
              {
                  "value": "Live",
                  "data":
                  {
                      "key": "1",
                      "value": "Live"
                  }
              },
              "description": "Belts",
              "tax_band": null,
              "created_at": null,
              "updated_at": "2014-07-21 12:36:39",
              "images": []
          },
          {
              "id": 216,
              "parent":
              {
                  "value": "Accessories",
                  "data":
                  {
                      "id": 16,
                      "parent": null,
                      "title": "Accessories",
                      "slug": "accessories",
                      "status":
                      {
                          "value": "Live",
                          "data":
                          {
                              "key": "1",
                              "value": "Live"
                          }
                      },
                      "description": "Shop for all your must have accessories!",
                      "tax_band": null,
                      "created_at": null,
                      "updated_at": "2014-07-21 12:36:38"
                  }
              },
              "title": "Necklaces",
              "slug": "necklaces",
              "status":
              {
                  "value": "Live",
                  "data":
                  {
                      "key": "1",
                      "value": "Live"
                  }
              },
              "description": "necklaces",
              "tax_band": null,
              "created_at": null,
              "updated_at": "2014-07-21 12:36:39",
              "images": []
          }
      ]
    }
  ]
}
```


### Example Empty Response
``` json
{
  "status": true,
  "result": []
}
```
<!--/code-->