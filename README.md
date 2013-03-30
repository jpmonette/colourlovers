# COLOURlovers API for Node.js

[COLOURlovers API for Node.js](https://npmjs.org/package/cnet) is a *connection library* for [COLOURlovers API](http://www.colourlovers.com/api), giving you access to an infinite database of colors, palettes, patterns and a lot more provided by [COLOURlovers](http://www.colourlovers.com/).

## Installation

```bash
$ npm install colourlovers
```

## Features

* Pure JavaScript
* Full access to COLOURlovers API
* Lightweight - 1 dependency only ([restler](https://npmjs.org/package/restler))!

## Quick Start

First, add the module to your project:

```js
var COLOURlovers = require('colourlovers');
```

Build your `HTTP` request using [COLOURlovers API Documentation](http://www.colourlovers.com/api). Here's an example requesting the `#FFFFFF` hexadecimal color using the `color` ressource:

```js
COLOURlovers.get('/color/FFFFFF', function(err, data) {
    if(err) throw err;
    console.log(data);
});
```

This will return you this `JSON` object:

```
http://www.colourlovers.com/api/color/FFFFFF?format=json
```

Here's a more complex `HTTP` request using the `palettes` ressource and a couple of `GET` parameters:

```js
colourlovers.get('/palettes', {
        hueOption:  'blue',
        keywords:   'chartreuse',
        sortBy:     'DESC',
        numResults: 20
    },function(err, data) {
    if(err) throw err;
    console.log(data);
});
```

This will return you this `JSON` object:

```
http://www.colourlovers.com/api/palettes?format=json&hueOptions=blue&keywords=chartreuse&sortBy=DESC&numResults=20
```

## Additional Information

By default, the module will return a `JSON` object. If you prefer to receive your data in `XML` format, populate the `format` key in your request `options` object like this:

```js
COLOURlovers.get('/colors', { format: 'xml' }, function(err, data) {
    if(err) throw err;
    console.log(data);
});
```

## More Information

* [COLOURlovers Official Website](http://www.colourlovers.com/)
* [COLOURlovers API for Node.js in the NPM Registry](http://npmjs.org/package/colourlovers)
* Follow me ([@jpmonette](https://twitter.com/jpmonette)) on Twitter for updates
* Read my personal blog [Blogue de Jean-Philippe Monette](http://blogue.jpmonette.net/) to learn more about what I do!

## License

Copyright (C) 2013, Jean-Philippe Monette <contact@jpmonette.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.