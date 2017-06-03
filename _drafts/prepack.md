---
layout: post
title: "Prepack"
date: 2017-06-06
tags: [prepack, preCompilingJavascript]
---

A few months ago we [watched](https://www.youtube.com/watch?v=xbZzahWakGs) a presentation on an intriguing and VERY experimental tech being developed at Facebook: the goal of this tech was to pre-compiled javascript to make it faster for evaluation.

Turns out this isn't experimental research anymore! This great [post](https://hackernoon.com/facebooks-prepack-the-next-killer-in-the-javascript-zone-d932556ffd8c) showcase how [Prepack](https://prepack.io/) can be used to dramatically speed up javascript.

Prepack uses the AST produce by Babel to optimize patterns and make a lot of "compile time" computations (and elimination) of code. This means the resulting javascript is lighter and thus faster to evaluate.

Some examples:

```javascript
(function () {
  function hello() { return 'hello'; }
  function world() { return 'world'; }
  global.s = hello() + ' ' + world();
})();
```

turns into this:

```javascript
(function () {
  s = "hello world";
})();
```

The classic Fibonacci function:

```javascript
(function () {
  function fibonacci(x) {
    return x <= 1 ? x : fibonacci(x - 1) + fibonacci(x - 2);
  }
  global.x = fibonacci(23);
})();
```

Turns into this constant thanks to unrolling of recursion:

```javascript
(function () {
  x = 28657;
})();
```

Where we will see a lot of speed improvements are on module initialization. One such example would be:

```javascript
(function () {
  let moduleTable = {};
  function define(id, f) { moduleTable[id] = f; }
  function require(id) {
    let x = moduleTable[id];
    return x instanceof Function ? (moduleTable[id] = x()) : x;
  }
  global.require = require;
  define("one", function() { return 1; });
  define("two", function() { return require("one") + require("one"); });
  define("three", function() { return require("two") + require("one"); });
  define("four", function() { return require("three") + require("one"); });
})();
three = require("three");
```

Which would be reduced to:

```javascript
(function () {
  function _2() {
    return 3 + 1;
  }

  var _1 = {
    one: 1,
    two: 2,
    three: 3,
    four: _2
  };

  function _0(id) {
    let x = _1[id];
    return x instanceof Function ? _1[id] = x() : x;
  }

  require = _0;
  three = 3;
})();
```

Lots more improvements are coming up in the next months. This technology could truly revolutionize web app performance.