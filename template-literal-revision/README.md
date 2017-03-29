# Template Literal Revision

For template literals in ES2016 some characters are not legal after a backslash(\\).

For example:

* \\u are reserved for unicode charaters and must look like \\u{1F4A4} or \\u004B
* \\x escape hex and must look like \\x4B
* \\ and digits starts an octal escape (such as \\141). Octal escapes are forbidden in template literals and strict mode string literals.

## Solution

```javascript
function tag(strs) {
  strs[0] === undefined
  strs.raw[0] === "\\unicode and \\u{55}";
}

tag`\unicode and \u{55}`

```

Untagged templates still throw an early error for invalid escape sequences:

```javascript
let bad = `bad escape sequence: \unicode`; // throws early error
```

Source:
[2ality](http://2ality.com/2016/09/template-literal-revision.html),
[TC-39](https://tc39.github.io/proposal-template-literal-revision/#sec-template-literal-lexical-components)
