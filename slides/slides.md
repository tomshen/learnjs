class: center, middle

# Programming in JavaScript
## Tom Shen

---

# Values
* `Number`
* `String`
* `Boolean`
* `Object`
* `Function`
* `Undefined`

---

# `Number`
* whole numbers: `42`, `-1`
* decimals: `9.81`
* scientific notation: `2.998e8`
* `Infinity`, `-Infinity`
* `NaN`: `0 / 0`, `Infinity - Infinity`

---

# `String`
* text: `'design'`, `"communication"`
* must be surrounded by *matching* **single** or double quotes
* all the text must fit on one line:

```js
'invalid
string'
```
* special characters
    * `\n`: newline
    * `\t`: tab
    * `\\`: backslash
    * `\'`: single quote

---

# `String` (continued)
```js
'This is the first line\nAnd this is the second'

'\'This is in quotes\''
```
becomes
```
This is the first line
And this the second

'This is in quotes'
```

---

# `Boolean`
* `true` / `false`

---

# `Object`
* maps *keys* to *values*
* "nouns" of a programming language

```js
{
    'make': 'Ford',
    'model': 'Mustang',
    'year': 1969
}
```

---

# `Object`: `Array`
* an `Array` is a common type of `Object`
* used to store a list of values:
    * `[1, 2, 3]`
* can hold values of different types:
    * `['foo', 'bar', -1, false]`

---

# `Function`
* "verbs" of a programming language

```js
function nextNumber (x) {
    return x + 1;
}
```

---
# Undefined values
* `undefined`, `null`
* used to indicate lack of value
* difference is subtle and mostly unimportant
* use `null`
