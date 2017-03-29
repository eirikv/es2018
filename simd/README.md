#SIMD (sim-dee)

SIMD står for Single-Instruction Multiple-Data (utalt "sim-dee").
SIMD gjør at vi kan utføre en instruks på et dataset )en vektor) med flere punkt.

## Single Instruction Single Data
![SISD](https://mdn.mozillademos.org/files/10509/SISD.png)

## Single Instruction Multiple Data
![SIMD](https://mdn.mozillademos.org/files/10507/SIMD.png)

```javascript
const a = SIMD.Float32x4(1, 2, 3, 4);
const b = SIMD.Float32x4(5, 6, 7, 8);
const c = SIMD.Float32x4.add(a,b); // Float32x4[6,8,10,12]
```

Source:
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SIMD),
[TC-39](https://github.com/tc39/ecmascript_simd/blob/master/tc39/SIMD-128%20TC-39.pdf)
