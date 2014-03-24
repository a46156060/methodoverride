# Method Override [![Build Status](https://travis-ci.org/fundon/koa-methodoverride.svg)](https://travis-ci.org/fundon/koa-methodoverride)
> HTTP method override for koa.

### Install

```
npm install koa-methodoverride
```

### Usage

```js
var app = require('koa')();
var parse = require('co-body');
var methodOverride = require('koa-methodoverride');

// First, must parse the body, use the `co-body` or the `koa-bodyparser` etc.
app.use(function *(next) {
  try {
    this.request.body = yield parse(this);
  } catch (e) {
    this.request.body = null;
  }
  yield next;
});

app.use(methodOverride());

app.listen(3000);
```

### Dependencies

* [co-body](https://github.com/visionmedia/co-body)
* Or other body parser


### License

MIT
