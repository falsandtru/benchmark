---
layout: bootstrap
title: 'Array outrange index access'
---

# Array outrange index access

Array negative number index access has large overhead.

```js
function benchmark(Benchmark) {
  var arr = [0];
  return new Benchmark.Suite()
    .add('exist number', function () {
      arr[0];
    })
    .add('outrange positive number', function () {
      arr[1];
    })
    .add('outrange negative number', function () {
      arr[-1];
    });
}
```
