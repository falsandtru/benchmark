---
layout: bootstrap
title: 'Object member access'
---

# Object member access

Some access method for object member has large overhead.

```js
function benchmark(Benchmark) {
  var obj = {};
  return new Benchmark.Suite()
    .add('dot', function () {
      obj.p;
    })
    .add('literal', function () {
      obj['p'];
    })
    .add('hasOwnProperty', function () {
      obj.hasOwnProperty('p');
    })
    .add('`in` operator', function () {
      'p' in obj;
    });
}
```
