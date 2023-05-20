# promise-note

## Promise Parallelism

```javascript
Promise.all([ p1, p2, p3])
  .then([ r1, r2, r3] => {
      console.log(r1, r2, r3)
    })
```

## Promise Sequential Execution

```javascript
Promise.resolve()
  .then(() => p1)
  .then(() => p2)
  .then(() => p3)
  .then(() => {
    console.log('done')
  })
```

## Promise Retry

```javascript
function retry(promiseFn, times, delay) {
  return new Promise((resolve, reject) => {
    const run = (count = 0) => {
      promiseFn()
        .then(resolve)
        .catch(err => {
          if (count === times) reject(err);
          else setTimeout(run, delay *= 2, count + 1);
        });
    };
    run();
  });
}
```
