# Images & Files

- [Introduction](#introduction)
- [Parameters](#params)
- [Object](#object)
- [Upload](#upload)
- [Single](#single)
- [Delete](#delete)
- [Order](#order)
- [Resize](#resize)

<a name="introduction"></a>
## Introduction

Within the API you can upload files and images to be stored on our edge-cached CDNs, making them available to your users faster and saving you bandwidth. Along with this we also provide services to resize, crop and scale images on the fly so you can implement them into any design, at any size you wish.

<a name="params"></a>
## Parameters

The parameters are the fields associated with this entry, as well as these there are a number of additional items - id, order, created_at, and updated_at. When submitting data to the API you should always use the key column and a value, rather than the name of the field.

Name | Key | Type | Required | Unique | Details
---- | --- | ---- | -------- | -------
Assign To | assign_to | Integer | Yes | No | The id of the entry to assign this file to
File | file | File | Yes | No | The file to upload, usually the path
Mime | mime | String | No | No | The mime type of the file, autodetected if not sent
Name | name | String | No | No | -

> **Note:** To upload a file you must set the content-type header to multipart/form-data.

<a name="object"></a>
## Object

    {
        "id": 56,
        "name": "artistscrayons.jpg",
        "url":
        {
            "http": "http://commercecdn.com/1/artistscrayons.jpg",
            "https": "https://commercecdn.com/1/artistscrayons.jpg"
        },
        "segments":
        {
            "domain": "commercecdn.com/",
            "suffix": "1/artistscrayons.jpg"
        }
    }

<a name="upload"></a>
## Upload

``` php
$result = File::Upload('<PARENT>', '<FILE PATH>');
```

<a name="single"></a>
## Single

``` php
$result = File::Get('<ID>');
```

<a name="delete"></a>
## Delete

``` php
$result = File::Delete('<ID>');
```

<a name="order"></a>
## Order

``` php
$result = File::Order([
	
]);
```

<a name="looping"></a>
## Looping

Flow entries that allow images to be stored will return an images array. We'll use [GET single product](product) in this example.

``` php
$product = Products::Get('<ID>');

foreach ($product['result']['images'] as $image) {
    echo "<img src='".$image['url']['http']."'/>";
}

```

<a name="resize"></a>
## Resize

You can use this to resize an images width, height and fill type. By combining this function with [looping](#looping) over an array of images you can resize multiple images.

``` php
function imageResize($image, $w = null, $h = null, $type = null)
{    
    if ( isset($image['segments']) )
    {
        $path = 'https://'.$image['segments']['domain'];
        
        if ($w) { $path .= '/w'.$w; }
        if ($h) { $path .= '/h'.$h; }
        if ($type) { $path .= '/'.$type; }
       
        $path .= '/'.$image['segments']['suffix'];
        
        return $path;
    }

    return $image['url']['https'];
}

echo '<img src="'.imageResize($product['image'], 150, 150).'" alt="Product image" />';
```
