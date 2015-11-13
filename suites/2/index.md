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
    .add('obj.p', function () {
      obj.p;
    })
    .add('obj["p"]', function () {
      obj['p'];
    })
    .add('obj.hasOwnProperty("p")', function () {
      obj.hasOwnProperty('p');
    })
    .add('"p" in obj', function () {
      'p' in obj;
    });
}
```
