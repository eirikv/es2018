# String.prototype

## trim

ES5 standardized String.prototype.trim. All major engines have also implemented corresponding trimLeft and trimRight functions - without any standard specification. For consistency with padStart/padRight we propose trimStart and trimEnd and trimLeft/trimRight as aliases required for web compatibility.

### trimStart

`trimStart` trims the start of a string. Example: `"    Hello World    ".trimStart(); // "Hello World    "`

### trimEnd

`trimEnd` trims the end of a string. Example: `"    Hello World    ".trimEnd(); // "    Hello World"`

Source:
[mdn]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/TrimLeft),
[TC-39](https://github.com/sebmarkbage/ecmascript-string-left-right-trim)
