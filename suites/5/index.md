---
layout: bootstrap
title: 'To string'
---

# To string

To string.

```js
function benchmark(Benchmark) {
  var val = 0;
  return new Benchmark.Suite()
    .add('+ ""', function () {
      val + '';
    })
    .add('String#toString', function () {
      val.toString();
    })
    .add('String()', function () {
      String(val);
    });
}
```
