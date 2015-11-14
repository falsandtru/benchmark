---
layout: bootstrap
title: 'Function call'
---

# Function call

Function call.

```js
function benchmark(Benchmark) {
  function f() {}
  return new Benchmark.Suite()
    .add('call', function () {
      f();
    })
    .add('Function#call', function () {
      f.call(this);
    })
    .add('Function#apply', function () {
      f.apply(this);
    });
}
```
