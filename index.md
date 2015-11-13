---
layout: bootstrap
title: JavaScript Benchmark on Browser
type: index
---

# JavaScript Benchmark on Browser

### Editable and Forkable <a class="benchmark-run btn btn-success btn-sm" href="https://github.com/falsandtru/benchmark"> Repo on GitHub</a>

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
