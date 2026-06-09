# Different Ways of Declaring Functions

JavaScript provides multiple ways to define functions depending on use case.

## Function Declaration

A standard way of defining a function.

```js
function greet() {
  console.log("Hello");
}
```

---

## Function Expression

A function stored inside a variable.

```js
const greet = function () {
  console.log("Hello");
};
```

---

## Arrow Function

A shorter syntax for defining functions.

```js
const greet = () => {
  console.log("Hello");
};
```

---

## Anonymous Function

A function without a name, usually used as a callback.

```js
setTimeout(function () {
  console.log("Executed");
}, 1000);
```

---

## IIFE (Immediately Invoked Function Expression)

A function that runs immediately after it is defined.

```js
(function () {
  console.log("Runs immediately");
})();
```

Output:

```txt
Runs immediately
```

---

## Key Points

- Function declarations are hoisted.
- Function expressions are not hoisted.
- Arrow functions are shorter and do not bind their own this.
- Anonymous functions are commonly used as callbacks.
- IIFEs run immediately after definition.
