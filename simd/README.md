# SIMD (sim-dee)

SIMD (pronounced "sim-dee") is short for Single Instruction/Multiple Data which is one classification of computer architectures. SIMD operations perform the same computation on multiple data points resulting in data level parallelism and thus performance gains, for example for 3D graphics and video processing, physics simulations or cryptography, and other domains.

## Single Instruction Single Data
![SISD](https://mdn.mozillademos.org/files/10509/SISD.png)

## Single Instruction Multiple Data
![SIMD](https://mdn.mozillademos.org/files/10507/SIMD.png)

### Code Example

```javascript
const a = SIMD.Float32x4(1, 2, 3, 4);
const b = SIMD.Float32x4(5, 6, 7, 8);
const c = SIMD.Float32x4.add(a,b); // Float32x4[6,8,10,12]
```

Source:
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SIMD),
[TC-39](https://github.com/tc39/ecmascript_simd/blob/master/tc39/SIMD-128%20TC-39.pdf)
