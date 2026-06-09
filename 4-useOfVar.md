# Why We Must Not Use var

## Definition

`var` is the old way of declaring variables and introduces several issues.

---

## Problem 1: Redeclaration

```js
var age = 20;
var age = 30;

console.log(age);
```

Output:

```txt
30
```

No error occurs.

---

## Problem 2: No Block Scope

```js
if (true) {
  var city = "Hyderabad";
}

console.log(city);
```

Output:

```txt
Hyderabad
```

The variable escapes the block.

---

## Problem 3: Hoisting Confusion

```js
console.log(name);

var name = "John";
```

Output:

```txt
undefined
```

This behavior often causes bugs.

---

## Key Points

- `var` ignores block scope.
- Redeclaration can hide mistakes.
- Modern JavaScript prefers `let` and `const`.
