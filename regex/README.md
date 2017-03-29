# Regexp

## Lookbehind Assertions

Positive Lookbehind: `(?<=...)`

Negative Lookbehind: `(?<!...)`

## Unicode Property Escapes

 Unicode property escapes of the form `\\p{…}` and `\\P{…}`.

* It is no longer painful to create Unicode-aware regular expressions.
* There is no dependency on run-time libraries.
* The regular expressions patterns are compact and readable — no more file size bloat.
* Creating a script that generates the regular expression at build time is no longer necessary.
* Code that uses Unicode property escapes stays up-to-date “automatically” from the developer’s point of view: whenever the Unicode Standard gets an update, the ECMAScript engine updates its data.

## Named Capture Groups

`(?<name>...)`

### Code Example

```regexp
/(\d{4})-(\d{2})-(\d{2})/

/(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/u
```

```javascript
let re = /(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/u;
let result = re.exec('2015-01-02');
// result.groups.year === '2015';
// result.groups.month === '01';
// result.groups.day === '02';

// result[0] === '2015-01-02';
// result[1] === '2015';
// result[2] === '01';
// result[3] === '02';
```


## s(dotAll) flag

---

Source:
[TC-39: Lookbehind](https://github.com/tc39/proposal-regexp-lookbehind),
[TC-39: Unicode](https://github.com/tc39/proposal-regexp-unicode-property-escapes),
[TC-39: Named Capture Groups](https://github.com/tc39/proposal-regexp-named-groups)
