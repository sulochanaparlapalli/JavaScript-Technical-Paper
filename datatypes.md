# Different Data Types in JavaScript

## Definition

A data type defines the type of value that a variable can store. JavaScript is a dynamically typed language, meaning the type of a variable is determined at runtime.

---

## Primitive Data Types

Primitive data types store a single value.

### String

Used to store text.

```js
let name = "John";
```

### Number

Used to store numeric values.

```js
let age = 25;
```

### Boolean

Stores either `true` or `false`.

```js
let isStudent = true;
```

### Undefined

A variable declared but not assigned a value.

```js
let city;
console.log(city);
```

Output:

```txt
undefined
```

### Null

Represents an intentional absence of value.

```js
let score = null;
```

### Symbol

Used to create unique identifiers.

```js
const id = Symbol("id");
```

### BigInt

Used for very large integers.

```js
const largeNumber = 12345678901234567890n;
```

---

## Non-Primitive Data Types

### Object

Stores key-value pairs.

```js
const user = {
  name: "John",
  age: 25
};
```

### Array

Stores multiple values.

```js
const colors = ["red", "blue", "green"];
```

### Function

Reusable block of code.

```js
function greet() {
  console.log("Hello");
}
```

---

## Key Points

- Primitive values are immutable.
- Objects and arrays are mutable.
- Functions are first-class objects in JavaScript.
