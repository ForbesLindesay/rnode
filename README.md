# rnode

Make node become really random, useful when checking you have no race conditions.

This adds a random delay to the async fuctions in node's modules:

 - fs
 - dns
 - child_process (exec and execFile only)

This random delay makes it much easier to spot if you are relying on timing of these async functions that might be working 90% of the time.  A random delay can make it fail more like 1 in 2 times.

[![Build Status](https://img.shields.io/travis/ForbesLindesay/rnode/master.svg)](https://travis-ci.org/ForbesLindesay/rnode)
[![Dependency Status](https://img.shields.io/david/ForbesLindesay/rnode.svg)](https://david-dm.org/ForbesLindesay/rnode)
[![NPM version](https://img.shields.io/npm/v/rnode.svg)](https://www.npmjs.com/package/rnode)

## Installation

    npm install rnode

## Usage

The API is simply `rnode(min, max)`, e.g.

```js
const rnode = require('rnode');
rnode('100 ms', '1 second');
```

You can pass either a string, as understood by the [ms](https://www.npmjs.com/package/ms) libarary, or a number of milliseconds.  The defaults are `0` and `500ms`.

## License

  MIT
