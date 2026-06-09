
# Function Hoisting

## Hoisting

Hoisting is JavaScript behavior where declarations are moved to the top of their scope during execution.

## Function Declaration Hoisting

Function declarations are fully hoisted, meaning both the name and the function body are available before execution starts.

---

## Example

```js
greet();

function greet() {
  console.log("Hello");
}
```

Output:

```txt
Hello
```

---

## Why It Works

JavaScript internally treats it like:

```js
function greet() {
  console.log("Hello");
}

greet();
```

---

## Function Expression Hoisting

Function expressions are not fully hoisted. Only the variable name is hoisted, not the function body.

---

```js
sayHi();

const sayHi = function () {
  console.log("Hi");
};
```

Output:

```txt
ReferenceError: Cannot access 'sayHi' before initialization
```

---

## Why It Fails

JavaScript internally treats it like:

```js
let sayHi;   // hoisted but not initialized

sayHi();     // error (cannot use before assignment)

sayHi = function () {
  console.log("Hi");
};
```

## Key Points

- Function declarations are fully hoisted.
- Function expressions are not usable before initialization.
- let and const stay in the Temporal Dead Zone.
- Avoid depending on hoisting for writing clean and predictable code
