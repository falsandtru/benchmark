---
layout: bootstrap
title: 'Arguments parameter'
---

# Arguments parameter

Arguments parameter.

```js
function benchmark(Benchmark) {
  var arr = [{}];
  function f(_) {}
  return new Benchmark.Suite()
    .add('array parameter', function () {
      f(arr);
    })
    .add('args parameter', function () {
      var args = [];
      for (var _i = 0; _i < arguments.length; _i++) {
        args[_i - 0] = arguments[_i];
      }
      f(args);
    })
    .add('arguments parameter', function () {
      f(arguments);
    });
}
```
