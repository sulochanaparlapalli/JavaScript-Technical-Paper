# Scope in JavaScript

## Definition

Scope determines where variables can be accessed in a program.

---

## Global Scope

Variables declared outside functions and blocks.

```js
let company = "Google";

function showCompany() {
  console.log(company);
}

showCompany();
```

Output:

```txt
Google
```

---

## Function Scope

Variables declared inside a function.

```js
function test() {
  let age = 25;
  console.log(age);
}

test();
```

Output:

```txt
25
```

Trying to access `age` outside the function causes an error.

---

## Block Scope

Variables declared using `let` or `const` inside blocks.

```js
if (true) {
  let city = "Bangalore";
  console.log(city);
}
```

Output:

```txt
Bangalore
```

Outside the block:

```js
console.log(city);
```

Output:

```txt
ReferenceError
```

---

## Key Points

- Global variables can be accessed anywhere.
- Function-scoped variables exist only inside functions.
- Block-scoped variables exist only inside blocks.
