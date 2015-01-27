class: center, middle

# Programming in JavaScript
## Tom Shen

---

# What Is Programming?

* Programming is manipulation of data
* A program is a set of instructions that can be understood by a computer

---

# Washing Clothes for a Human
1. Put the clothes in the machine
2. Add detergent to the machine
3. Turn on the washing machine
4. Wait an hour for the machine to finish running
5. Take clothes out of the machine

---

# Washing Clothes for a Computer
```js
var washingMachine = new WashingMachine();
var clothes = ['shirt', 'pants', 'socks'];
var tide = 'Tide';

// 1. Put the clothes in the machine
clothes.forEach(function (item) {
    washingMachine.add(item);
});

// 2. Add detergent to the machine
washingMachine.add(tide);

// 3. Turn on the washing machine
washingMachine.wash();

// 4. Wait an hour for the machine to finish running
setTimeout(function () {
    // 5. Take clothes out of the machine
    washingMachine.empty();
}, 1000 * 60 * 60);

```

---

# Programming Languages
* Instructions for humans can be in English, Spanish, Chinese, etc.
* Instructions for computers can be in C, Java, Python, JavaScript, etc.

---

# JavaScript
* Language of the web: the only language web browsers understand
* Not just for the web
* Very popular (7th most popular programming language as of January 2015, according to TIOBE)
* **Not related to Java**

---

# Values

* Programming is manipulation of data
* Chunks of data in JavaScript are called *values*
* There are *six* types of values in JavaScript

---

# Types of Values
* `Number`
* `String`
* `Boolean`
* `Object`
* `Function`
* undefined

---

# Variables
* define variables with the notation:
```js
var one = 1;
```
* `one` is the name of the variable
* refer to variables by their names
* `1` is the value the variable refers to

---

# `Number`
* `-1.8e308` to `1.8e308`
* not exact for very large or very small numbers
* whole numbers: `42`, `-1`
* decimals: `9.81`
* scientific notation: `2.998e8`, `6.626e-34`
* `Infinity`, `-Infinity`
* not a number: `NaN`, `0 / 0`, `Infinity - Infinity`

---

# `String`
* text: `'design'`, `"communication"`
* must be surrounded by *matching* single or double quotes
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

# `String`
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

# Operators
* `+`, `-`, `/`, `*`, `%`
* `===`, `<`, `>`, `<=`, `>=`
* `+`
* `!`, `&&`, `||`
* `==` can be used to check for equality, but has inconsistent behavior

---

# Operators
```js
(100 + 4) * 11 === 104 * 11 === 1144

5 < 4 === false

'foo' + 'bar' === 'foobar'

!false === true

true && true === true

true && false === false

false && false === false

true || true === true

true || false === true

false || false === false
```

---

# Operators
* `x++` is the same as `x = x + 1`
* `x += 5` is the same as `x = x + 5`
* this applies for `-`, `*`, `/`, `%`

---

# `Object`
* maps `String`s to *values*

```js
var car = {
    'make': 'Ford',
    'model': 'Mustang',
    'year': 1969
};

car.make === 'Ford'
car['make'] === 'Ford'
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
* take in values as inputs
* return nothing (undefined) or a value

```js
function nextNumber (x) {
    return x + 1;
}
var nextNumber = function (x) {
    return x + 1;
};
```

---

# Calling Functions
* `1` is the input to `nextNumber`
* it adds `1` to it, and returns `2`
* `y` is now set to `2`

```js
var y = nextNumber(1);
```

---

# Higher-order Functions
* Since functions are values, they can be used as input to a function or be the out put of a function
```js
setTimeout(function () {
    washingMachine.empty();
}, 1000 * 60 * 60);
```

---

# Defining New Objects
* `Function`s are technically `Object`s too
* `this` can be used to refer to an `Object`'s properties

```js
function WashingMachine() {
    this.contents = [];
    this.running = false;
}

var washingMachine = new WashingMachine();
```

* `new` means to create a new *instance* of `WashingMachine`
* `WashingMachine` is a *prototype* for building instances of washing machine objects
* on every instance of `WashingMachine`, `contents` and `running` are *properties* defined on it
* `washingMachine.contents` is `[]`, and `washingMachine.running` is `false`

---

# Defining Methods on Objects
* *methods* are `Function`s defined on `Object`s
* they let you define ways to manipulate the data stored in an object's properties

```js
WashingMachine.prototype.add = function (item) {
    this.contents.push(item);
    console.log('Adding', item)
};

washingMachine.add('tide');
```

* `add` is a method defined on the prototype of `WashingMachine`
* this means when we construct new instances of `WashingMachine`, they will have `add` defined on them

---

# `console.log`
* takes in one or more values as inputs
* converts all of them to `String`s
* prints them out, separated by spaces

---

# Undefined values
* used to indicate lack of value
* `undefined`, `null`
* difference is subtle and mostly unimportant
* use `null`
* a function that returns nothing technically returns `undefined`

---

# Type Conversion
* `parseInt(s, 10)` converts the `String` `s` to a whole `Number`
* `parseFloat(s)` converts the `String` `s` to a decimal number
* `Number(n).toString()` converts the `Number` `n` to a `String`
* `Boolean(b).toString()` converts the `Boolean` `b` to a `String`
* `JSON.stringify(o)` converts the `Object` `o` to a `String`
* `JSON.parseJSON(s)` converts the `String` `s` to an `Object`

---

# Falsey
* non-`Boolean` values that can be treated as false
* `0`, `''`, `undefined`, `null`
* Note that none of them are `===` to false

---

# Statements
* a statement is a single instruction, or many instructions grouped together

---

# Statements: Variables
* variable declarations and initialization

```js
var x;

var y = 5;

x = 'foo';

var nextNumber = function (x) {
    return x + 1;
};
```
* should always end with semicolons

---

# Statements: Functions
* function declarations

```js
function nextNumber (x) {
    return x + 1;
}
```

---

# Statements: Control Flow
```js
var running = false;
if (running) {
    console.log('running');
} else {
    console.log('not running');
}
```
* other control statements include `switch/continue/break`, `throw`, and `try/catch`
* don't worry about them for now

---

# Statements: Iteration
* iteration statements are for running the same set of instructions multiple times

```js
var x = 0;
while (x < 10) {
    x = x + 1;
}

var sum = 0;
for (var i = 0; i < 10; i++) {
    sum += i;
}
```

---

# Comments
* a comment is a line in the program or a section of code in the program you want the computer to ignore

```js
// ignore this line

var x = 5; // ignore everything after the //

var x = /* ignore me */ 6;

/* ignore
these lines 
too */
```

---

# Washing Machine
```js
function WashingMachine() {
    this.contents = [];
    this.running = false;
}
WashingMachine.prototype.add = function (item) {
    this.contents.push(item);
    console.log('Adding', item)
};
WashingMachine.prototype.empty = function () {
    if (this.running) {
        this.running = false;
    }
    while (this.contents.length > 0) {
        var item = this.contents.pop();
        console.log('Removing', item);
    } 
};
WashingMachine.prototype.wash = function () {
    if (!this.running) {
        this.running = true;
    }
}
```

---

# Conclusion
* This is only a small portion of what JavaScript the language offers.
* We haven't even delved into the *libraries* that come with JavaScript.
    * *Libraries* are programs that other people have written and tested.
    * You can use in your own programs to reduce the amount of code you have to write.
* The best way to learn JavaScript (and programming in general) is to write programs.
