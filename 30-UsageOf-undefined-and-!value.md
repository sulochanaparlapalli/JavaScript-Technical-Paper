# Why `value === undefined` Is Better Than `!value`

## Definition

Both `value === undefined` and `!value` are often used to check whether a value exists.

However, they do **not** mean the same thing.

Using `value === undefined` is more precise because it checks only for `undefined`, while `!value` treats many valid values as missing.

---

## Using `!value`

The `!` operator converts a value to a boolean and then reverses it.

```js
const value = "";

console.log(!value);
```

Output:

```txt
true
```

---

## Falsy Values

JavaScript considers the following values as falsy:

```js
false
0
-0
0n
""
null
undefined
NaN
```

Example:

```js
console.log(!false);
console.log(!0);
console.log(!"");
console.log(!undefined);
```

Output:

```txt
true
true
true
true
```

---

## Problem with `!value`

Sometimes values like `0` or `""` are perfectly valid.

```js
const quantity = 0;

if (!quantity) {
  console.log("Quantity is missing");
}
```

Output:

```txt
Quantity is missing
```

This is incorrect because `0` is a valid quantity.

---

## Using `value === undefined`

```js
const quantity = 0;

if (quantity === undefined) {
  console.log("Quantity is missing");
}
```

Output:

```txt
Nothing prints
```

Now the check is accurate.

---

# Example 1: User Age

### Wrong

```js
const age = 0;

if (!age) {
  console.log("Age not provided");
}
```

Output:

```txt
Age not provided
```

Age `0` is valid for a newborn.

---

### Correct

```js
const age = 0;

if (age === undefined) {
  console.log("Age not provided");
}
```

Output:

```txt
Nothing prints
```

---

# Example 2: Empty String

### Using `!value`

```js
const username = "";

if (!username) {
  console.log("Username missing");
}
```

Output:

```txt
Username missing
```

Sometimes an empty string might be a valid value depending on the application.

---

### Using `=== undefined`

```js
const username = "";

if (username === undefined) {
  console.log("Username missing");
}
```

Output:

```txt
Nothing prints
```

---

# Example 3: Boolean Values

### Problem

```js
const isAdmin = false;

if (!isAdmin) {
  console.log("Value missing");
}
```

Output:

```txt
Value missing
```

But `false` is a valid value.

---

### Better

```js
const isAdmin = false;

if (isAdmin === undefined) {
  console.log("Value missing");
}
```

Output:

```txt
Nothing prints
```

---

# Visual Comparison

## `!value`

Checks:

```txt
false
0
-0
0n
""
null
undefined
NaN
```

All return `true`.

---

## `value === undefined`

Checks only:

```txt
undefined
```

Nothing else matches.

---

# When to Use `!value`

Use it when you want to reject **all falsy values**.

Example:

```js
const password = "";

if (!password) {
  console.log("Password is required");
}
```

Output:

```txt
Password is required
```

Here an empty string should be rejected.

---

# When to Use `value === undefined`

Use it when you specifically want to know whether a variable was never assigned a value.

Example:

```js
function greet(name) {
  if (name === undefined) {
    name = "Guest";
  }

  console.log(name);
}
```

This avoids accidentally treating valid values as missing.

---

# Modern Alternative: Nullish Check

Sometimes you want to check for both `null` and `undefined`.

```js
if (value == null) {
  console.log("Missing");
}
```

This matches:

```txt
null
undefined
```

but not:

```txt
0
false
""
```

---

# Real-World Example

### Buggy Code

```js
function calculateDiscount(discount) {
  if (!discount) {
    discount = 10;
  }

  return discount;
}

console.log(calculateDiscount(0));
```

Output:

```txt
10
```

The user intentionally passed `0`, but it gets replaced.

---

### Correct Code

```js
function calculateDiscount(discount) {
  if (discount === undefined) {
    discount = 10;
  }

  return discount;
}

console.log(calculateDiscount(0));
```

Output:

```txt
0
```

Now the function behaves correctly.

---

# Best Practice

Use:

```js
value === undefined
```

when checking whether a value was not provided.

Use:

```js
!value
```

when you intentionally want to reject all falsy values.

---

# Key Points

- `!value` checks for all falsy values.
- `value === undefined` checks only for `undefined`.
- `!value` can accidentally reject valid values like `0`, `false`, and `""`.
- `value === undefined` is more precise and safer.
- Use explicit checks when you care about the exact value.
- Understanding this difference helps prevent many real-world bugs.
