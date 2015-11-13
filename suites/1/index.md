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
    .add('Array exist number index access', function () {
      arr[0];
    })
    .add('Array outrange positive number index access', function () {
      arr[1];
    })
    .add('Array outrange negative number index access', function () {
      arr[-1];
    });
}
```
