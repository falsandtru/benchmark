---
layout: bootstrap
title: 'Worker messaging'
---

# Worker messaging

Worker messaging.

```js
function benchmark(Benchmark) {
  var blob = new Blob([onmessage].map(function (f) { return f.toString().slice(f.toString().indexOf(')') + 1); }), {type: "text/javascript"}),
      worker = new Worker(window.URL.createObjectURL(blob)),
      shared = new SharedWorker(window.URL.createObjectURL(blob));
  function onmessage() {
    self.onmessage = function(event) {
      self.postMessage(event.data);
    }
    self.onconnect = function(e) {
      var port = e.ports[0];
      port.onmessage = function(e) {
        port.postMessage(e.data);
      }
    }
  }

  var str = 'msg',
      arr = [str],
      obj = {msg: str};

  worker.onmessage = function (event) {
    event.data;
  };

  shared.port.start();
  shared.port.onmessage = function (event) {
    event.data;
  };
  return new Benchmark.Suite()
    .add('worker string', function () {
      worker.postMessage(str);
    })
    .add('worker array', function () {
      worker.postMessage(arr);
    })
    .add('worker object', function () {
      worker.postMessage(obj);
    })
    .add('shared string', function () {
      shared.port.postMessage(str);
    })
    .add('shared array', function () {
      shared.port.postMessage(arr);
    })
    .add('shared object', function () {
      shared.port.postMessage(obj);
    })
    .add('promise then', function () {
      Promise.resolve().then(function () {});
    });
}
```
