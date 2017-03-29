# Asynchronous Iteration (for-await-of)

A JavaScript Iterator is an object with a .next() method, which returns an IteratorItem, which is an object with value : <any> and done : <boolean>.

A JavaScript AsyncIterator is an object with a .next() method, which returns a Promise<IteratorItem>, a promise for the next value.

## Solution

```javascript
/**
 * Returns a promise which resolves after time had passed.
 */
const delay = time => new Promise(resolve => setTimeout(resolve, time));

async function* delayedRange(max) {
  for (let i = 0; i < max; i++) {
    await delay(1000);
    yield i;
  }
}

for await (let number of delayedRange(10)) {
  console.log(number);
}
```

Source:
[Stackoverflow](http://stackoverflow.com/documentation/javascript/5807/async-iterators#t=20170329180527783051),
[TC-39](https://github.com/tc39/proposal-async-iteration)
