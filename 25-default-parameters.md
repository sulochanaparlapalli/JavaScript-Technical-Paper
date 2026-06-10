# Default Parameters

## Definition

Default parameters allow you to assign default values to function parameters.

If an argument is not provided when the function is called, the default value is used.

Default parameters were introduced in ES6 (ECMAScript 2015).

---

## Syntax

```js
function greet(name = "Guest") {
  console.log(`Hello ${name}`);
}
```

---

## Example Without an Argument

```js
function greet(name = "Guest") {
  console.log(`Hello ${name}`);
}

greet();
```

Output:

```txt
Hello Guest
```

Since no value was passed, `"Guest"` is used.

---

## Example With an Argument

```js
function greet(name = "Guest") {
  console.log(`Hello ${name}`);
}

greet("John");
```

Output:

```txt
Hello John
```

Since a value was passed, the default value is ignored.

---

## Multiple Default Parameters

```js
function createUser(name = "Unknown", age = 18) {
  console.log(`${name} is ${age} years old`);
}

createUser();
```

Output:

```txt
Unknown is 18 years old
```

---

## Overriding Some Parameters

```js
function createUser(name = "Unknown", age = 18) {
  console.log(`${name} is ${age} years old`);
}

createUser("John");
```

Output:

```txt
John is 18 years old
```

Only the first parameter is overridden.

---

## Using Expressions as Default Values

Default values can be expressions.

```js
function calculatePrice(price, tax = price * 0.1) {
  return price + tax;
}

console.log(calculatePrice(100));
```

Output:

```txt
110
```

The default tax is calculated from the price.

---

## Using Functions as Default Values

```js
function getCurrentYear() {
  return 2026;
}

function showYear(year = getCurrentYear()) {
  console.log(year);
}

showYear();
```

Output:

```txt
2026
```

A function can generate the default value.

---

## Default Parameters and Undefined

Default values are applied only when the argument is `undefined`.

```js
function greet(name = "Guest") {
  console.log(name);
}

greet(undefined);
```

Output:

```txt
Guest
```

---

## Default Parameters and Null

```js
function greet(name = "Guest") {
  console.log(name);
}

greet(null);
```

Output:

```txt
null
```

`null` is treated as a real value, so the default value is not used.

---

## Old Way Before ES6

Before default parameters existed, developers often used logical OR (`||`).

```js
function greet(name) {
  name = name || "Guest";

  console.log(`Hello ${name}`);
}

greet();
```

Output:

```txt
Hello Guest
```

---

## Problem with the Old Way

```js
function showCount(count) {
  count = count || 10;

  console.log(count);
}

showCount(0);
```

Output:

```txt
10
```

This is incorrect because `0` is a valid value.

---

## Modern Solution

```js
function showCount(count = 10) {
  console.log(count);
}

showCount(0);
```

Output:

```txt
0
```

Default parameters handle this correctly.

---

## Real-World Example

```js
function createProduct(
  name = "Unknown Product",
  price = 0,
  category = "General"
) {
  return {
    name,
    price,
    category
  };
}

console.log(createProduct());
```

Output:

```js
{
  name: "Unknown Product",
  price: 0,
  category: "General"
}
```

---

## Key Points

- Default parameters provide fallback values.
- Introduced in ES6.
- Applied only when the argument is `undefined`.
- Can use expressions as default values.
- Can use function calls as default values.
- Improve readability and maintainability.
- Better than the old `||` fallback technique.
- Commonly used in modern JavaScript applications.
