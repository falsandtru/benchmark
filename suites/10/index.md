---
layout: bootstrap
title: 'Global variable reference'
---

# Global variable reference

Global variable reference.

```js
function benchmark(Benchmark) {
  var Arr = Array;
  return new Benchmark.Suite()
    .add('Global variable reference', function () {
      Array;
    })
    .add('Global variable reference x10', function () {
      Array; Array; Array; Array; Array;
      Array; Array; Array; Array; Array;
    })
    .add('Instantiation of global variable', function () {
      new Array();
    })
    .add('Local variable reference', function () {
      Arr;
    })
    .add('Instantiation of local variable', function () {
      new Arr();
    });
}
```
