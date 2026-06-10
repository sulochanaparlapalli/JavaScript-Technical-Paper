# Variable Number of Arguments Passed to Functions

## Definition

Sometimes we don't know how many arguments will be passed to a function.

JavaScript allows functions to accept a variable number of arguments using the **Rest Parameter (`...`)**.

---

# Rest Parameter (`...args`)

```js
function showArgs(...args) {
  console.log(args);
}

showArgs(1, 2, 3, 4);
```

Output:

```txt
[1, 2, 3, 4]
```

All arguments are collected into an array.

---

# Sum Multiple Numbers

```js
function sum(...numbers) {
  return numbers.reduce(
    (total, num) => total + num,
    0
  );
}

console.log(sum(10, 20));
console.log(sum(10, 20, 30, 40));
```

Output:

```txt
30
100
```

---

# Count Arguments

```js
function countArgs(...args) {
  return args.length;
}

console.log(countArgs(1, 2, 3, 4));
```

Output:

```txt
4
```

---

# Mixing Regular and Rest Parameters

```js
function introduce(name, ...hobbies) {
  console.log(name);
  console.log(hobbies);
}

introduce(
  "John",
  "Reading",
  "Coding"
);
```

Output:

```txt
John
["Reading", "Coding"]
```

The rest parameter must be the last parameter.

---

# The `arguments` Object (Older Method)

```js
function showArgs() {
  console.log(arguments);
}

showArgs(1, 2, 3);
```

Output:

```txt
Arguments(3) [1, 2, 3]
```

Before ES6, `arguments` was used to access all arguments.

---

# Arrow Function Example

```js
const showArgs = (...args) => {
  console.log(args);
};

showArgs("A", "B", "C");
```

Output:

```txt
["A", "B", "C"]
```

Arrow functions use rest parameters because they do not have their own `arguments` object.

---

# Common Rules

### Only One Rest Parameter

```js
function test(...args) {}
```

---

### Must Be Last

Correct

```js
function test(name, ...args) {}
```

Wrong

```js
function test(...args, name) {}
```

---

```js
function test(...args, name) {}
```

---

# Real-World Example

```js
function log(...messages) {
  messages.forEach(message =>
    console.log(message)
  );
}

log(
  "Server Started",
  "Database Connected",
  "User Logged In"
);
```

Output:

```txt
Server Started
Database Connected
User Logged In
```

---

# Key Points

- Use `...args` when the number of arguments is unknown.
- Rest parameters collect arguments into an array.
- A function can have only one rest parameter.
- The rest parameter must be the last parameter.
- `arguments` is the older approach.
- Prefer rest parameters in modern JavaScript.
