---
layout: bootstrap
title: 'Array item removal'
---

# Array item removal

Array item removal.

```js
function benchmark(Benchmark) {
  var arr = [0],
      index = 0;
  return new Benchmark.Suite()
    .add('Array#shift', function () {
      arr.push(0);
      arr.shift();
    })
    .add('Array#pop', function () {
      arr.push(0);
      arr.pop();
    })
    .add('Array#splice', function () {
      arr.push(0);
      arr.splice(0, 1);
    })
    .add('dynamic switching', function () {
      arr.push(0);
      switch (index) {
        case -1: {
          break;
        }
        case 0: {
          arr.shift();
          break;
        }
        default: {
          arr.splice(index, 1);
        }
      }
    });
}
```
