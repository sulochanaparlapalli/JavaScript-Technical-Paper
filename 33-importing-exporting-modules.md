# Importing and Exporting Modules Using `require()` and `module.exports`

## Definition

Node.js allows code to be split into multiple files called **modules**.

Modules help organize code, improve readability, and make applications easier to maintain.

In the CommonJS module system used by Node.js:

- `module.exports` is used to export code from a file.
- `require()` is used to import code into another file.

---

# Why Use Modules?

Without modules, all code would exist in one large file.

```txt
app.js
├── Database Code
├── Authentication Code
├── Utility Functions
├── Business Logic
└── API Routes
```

Large files become difficult to manage.

Modules allow code to be separated into smaller files.

```txt
project/
│
├── app.js
├── math.js
├── user.js
└── utils.js
```

---

# Creating Your First Module

## math.js

```js
function add(a, b) {
  return a + b;
}

module.exports = add;
```

This exports the `add` function.

---

## app.js

```js
const add = require("./math");

console.log(add(10, 20));
```

Output:

```txt
30
```

---

# How `require()` Works

```js
const add = require("./math");
```

Explanation:

```txt
require("./math") -> Loads math.js -> Returns module.exports
```

---

# Exporting Multiple Functions

## math.js

```js
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = {
  add,
  subtract
};
```

---

## app.js

```js
const math = require("./math");

console.log(math.add(10, 5));
console.log(math.subtract(10, 5));
```

Output:

```txt
15
5
```

---

# Object Destructuring with require()

Instead of:

```js
const math = require("./math");

math.add();
math.subtract();
```

You can use destructuring:

```js
const { add, subtract } = require("./math");

console.log(add(10, 5));
console.log(subtract(10, 5));
```

Output:

```txt
15
5
```

This is cleaner and commonly used.

---

# Exporting Variables

## config.js

```js
const PORT = 3000;

module.exports = PORT;
```

---

## app.js

```js
const PORT = require("./config");

console.log(PORT);
```

Output:

```txt
3000
```

---

# Exporting Objects

## user.js

```js
const user = {
  name: "John",
  age: 25
};

module.exports = user;
```

---

## app.js

```js
const user = require("./user");

console.log(user.name);
```

Output:

```txt
John
```

---

# Exporting Arrays

## colors.js

```js
const colors = ["Red", "Green", "Blue"];

module.exports = colors;
```

---

## app.js

```js
const colors = require("./colors");

console.log(colors);
```

Output:

```txt
["Red", "Green", "Blue"]
```

---

# Exporting Anonymous Functions

## logger.js

```js
module.exports = function () {
  console.log("Application Started");
};
```

---

## app.js

```js
const logger = require("./logger");

logger();
```

Output:

```txt
Application Started
```

---

# Module Caching

A module is loaded only once.

## counter.js

```js
console.log("Counter module loaded");

module.exports = {};
```

---

## app.js

```js
require("./counter");
require("./counter");
require("./counter");
```

Output:

```txt
Counter module loaded
```

Even though `require()` is called three times, the module runs only once.

Node.js caches loaded modules.

---

# File Extensions

These are equivalent:

```js
require("./math");
```

```js
require("./math.js");
```

Most developers omit the `.js` extension.

---

# Relative Paths

### Current Folder

```js
require("./math");
```

---

### Parent Folder

```js
require("../math");
```

---

### Nested Folder

```js
require("./utils/math");
```

---

# Common Mistake

### Forgetting `./`

Wrong

```js
require("math");
```

Node.js will search inside:

```txt
node_modules
```

---

Correct

```js
require("./math");
```

This tells Node.js to load a local file.

---

# CommonJS Module Pattern

## calculator.js

```js
function add(a, b) {
  return a + b;
}

function multiply(a, b) {
  return a * b;
}

module.exports = {
  add,
  multiply
};
```

---

## app.js

```js
const { add, multiply } = require("./calculator");

console.log(add(2, 3));
console.log(multiply(2, 3));
```

Output:

```txt
5
6
```

---

# Difference Between `exports` and `module.exports`

### Valid

```js
module.exports = {
  add,
  subtract
};
```

---

### Also Valid

```js
exports.add = add;
exports.subtract = subtract;
```

---

### Problematic

```js
exports = {
  add,
  subtract
};
```

This does not work as expected.

Always prefer:

```js
module.exports
```

because it is clearer and less error-prone.

---

# Real-World Example

## userService.js

```js
function getUsers() {
  return ["John", "Sara", "Mike"];
}

module.exports = {
  getUsers
};
```

---

## app.js

```js
const { getUsers } = require("./userService");

console.log(getUsers());
```

Output:

```txt
["John", "Sara", "Mike"]
```

---

# Benefits of Modules

- Better code organization.
- Easier maintenance.
- Reusable code.
- Reduced duplication.
- Cleaner project structure.
- Easier collaboration among developers.

---

# Key Points

- Node.js uses the CommonJS module system by default.
- `module.exports` exports data from a file.
- `require()` imports data from another file.
- You can export functions, objects, arrays, variables, or classes.
- Use destructuring when importing multiple exports.
- Modules are cached after the first load.
- Use `./` when importing local files.
- Prefer `module.exports` over reassigning `exports`.
- Modules help build scalable and maintainable applications.
