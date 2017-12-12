# Compressor Head

Compressor Head is a web application for compressing/scaling and changing format (Supported formats - JPEG, PNG and WEBP) of an image to the desired form. After getting your desired form, you can download it.
It is built on [Python](https://www.python.org) and hosted on the [Google App Engine](https://cloud.google.com/appengine).

## Why Compressor Head?

Compressor Head compresses image to the desired resolution and also changes it to the desired format before passing the image back to the user to download. It is fast and also saves data and storage resources.

If you run it on the Google App Engine, the image converts in an instant. The usage of the memcache library also speeds up the conversion process (if the same image has been retrieved previously).

## Contents
* [Usage](#usage)
* [Usage example](#usage_exm)
* [Working with the project](#work)
* [API reference](#ref)
* [Author](#author)
* [Copyright](#copyright)

### <a id="usage"></a>Usage

*URL* - 
Copy the URL from here and fill the required information accordingly-
```http://compressor-head.appspot.com/image/?image_url=[IMAGE_URL]&width=[WIDTH]&height=[HEIGHT]&format=[FORMAT]```

Where
```
[IMAGE_URL] is the URL of the image which is to be compressed.
[WIDTH] is the desired width of the image.
[HEIGHT] is the desired height of the image.
[FORMAT] is the desired image format (Supported formats - JPEG, PNG and WEBP).
```

Both WIDTH and HEIGHT should be zero or positive integers 
 * If *both are zero*, the image will not be compressed/scaled.
 * If *one of the two is zero*, it will scale in such a way that non-zero dimension and the other dimention will be scaled such that the aspect ratio remains the same.
 * If *both are not zero*, both dimentions will scale accordingly.

### <a id="usage_exm"></a>Usage example

Sample Image URL - http://compressor-head.appspot.com/image
This is a `5.8 MB JPEG` image with dimentions `5649×3684`.
![](http://compressor-head.appspot.com/image)

To resize the image -
- Resize (Width) : `http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=500&height=0&format=jpeg`

![](http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=500&height=0&format=jpeg)

This returns an image `37 KB JPEG` image with dimentions `500x326`.

- Resize (Height) : `http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=0&height=250&format=png`

![](http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=0&height=250&format=png)

This returns an image `164 KB PNG` image with dimentions `383x250`.

- Resize (Width & Height) : `http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=500&height=350&format=jpeg`

![](http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=500&height=350&format=jpeg)

This returns an image `41 KB JPEG` image with dimentions `500x350`.

**Note:** You can also use the `WEBP` format (it's not shown here as an example because GitHub does not render WEBPs). A sample WEBP conversion of this conversion can be found [here](http://compressor-head.appspot.com/image/?image_url=http://compressor-head.appspot.com/image&width=500&height=350&format=webp).

### <a id="work"></a> Working with the project

If you'd like to get more hands on the project, check out the following documentation:
 * [Setting up the project](doc/SETUP.md)
 * [Contributing to the project](doc/CONTRIBUTING.md)

### <a id="ref"></a>API reference

 * [Google App Engine (Python): Images API](https://cloud.google.com/appengine/docs/standard/python/refdocs/google.appengine.api.images.html)
 * [Google App Engine (Python): Memcache API](https://cloud.google.com/appengine/docs/standard/python/refdocs/google.appengine.api.memcache.html)
 * [Google App Engine (Python): URL downloading API](https://cloud.google.com/appengine/docs/standard/python/refdocs/google.appengine.api.urlfetch.html)
 * [Vinay Sajip: logging](http://www.red-dove.com/python_logging.html)
 * [The Webapp2 Maintainers: webapp2](https://cloud.google.com/appengine/docs/standard/python/refdocs/google.appengine.api.images.html)

### <a id="author"></a>Author

[@m-murad](https://github.com/m-murad)

## <a id="copyright"></a>Copyright

    Copyright 2017 Murad. All rights reserved.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
