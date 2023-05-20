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
