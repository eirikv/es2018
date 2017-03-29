# Rest/Spread Properties

## Rest Properties

### Code Example

```javascript
const { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
console.log(x); // 1
console.log(y); // 2
console.log(z); // { a: 3, b: 4 }
```

### Code Example

## Spread Properties

```javascript
const n = { x, y, ...z };
console.log(n); // { x: 1, y: 2, a: 3, b: 4 }
```

---

Source: [Babeljs](https://babeljs.io/docs/plugins/transform-object-rest-spread/)
