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
    .add('arr[0]: exist number', function () {
      arr[0];
    })
    .add('arr[1]: outrange positive number', function () {
      arr[1];
    })
    .add('arr[-1]: outrange negative number', function () {
      arr[-1];
    });
}
```
