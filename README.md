hr.backend [![Build Status](https://travis-ci.org/HappyRhino/hr.backend.png?branch=master)](https://travis-ci.org/HappyRhino/hr.backend)
=============================

> Backend with fallback

## Installation

```
$ npm install hr.backend
```

### Documentation

```js
var Backend = require("hr.backend");

var myApi = new Backend({

});

// Handle api method
myApi.defaultMethod({
    execute: function(args, options, method) {
        return doSomeHttpStuff(method, args);
    }
});

// Ask to cache the method "GET:posts"
myApi.addCachedMethod("GET:posts");

// Execute an api call
myApi.execute("GET:posts")
.then(function(results) {
    // Results will come from the http server or the cache if offline
});
```
