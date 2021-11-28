#### Promise.race

```js
Promise.race = function(iterators) {
  return new Promise((resole, reject) => {
    for (const iter of iterators) {
      Promise.resolve(iter)
      .then((res) => {
        resolve(res);
      })
      .catch((err) => {
        reject(err);
      })
    }
  })
}
```

<a href="https://github.com/rxaviers/async-pool">async-pool</a>