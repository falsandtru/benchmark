---
layout: bootstrap
title: 'Template'
---

# Template

Description.

```js
function benchmark(Benchmark) {
  var arr = [0];
  return new Benchmark.Suite()
    .add('Array exist index access', function () {
      arr[0];
    })
    .add('Array outrange positive index access', function () {
      arr[1];
    })
    .add('Array outrange negative index access', function () {
      arr[-1];
    });
}
```
