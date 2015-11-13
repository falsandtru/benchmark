---
layout: bootstrap
title: 'Array copy'
---

# Array copy

Array copy.

```js
function benchmark(Benchmark) {
  var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
  return new Benchmark.Suite()
    .add('slice', function () {
      arr.slice();
    })
    .add('concat', function () {
      arr.concat();
    })
    .add('manipulate', function () {
      var arr2 = [];
      for (var i = 0; i < arr.length; i++) {
        arr2[i] = arr[i];
      }
    });
}
```
