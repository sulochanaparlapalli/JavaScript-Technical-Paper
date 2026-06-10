# Difference Between `==` and `===`

## Definition

Both `==` and `===` are comparison operators used to compare values in JavaScript.

The main difference is:

- `==` compares values after type conversion (type coercion).
- `===` compares both value and data type without type conversion.

Because of this, `===` is generally recommended.

---

## Double Equals (`==`)

The `==` operator checks whether two values are equal after converting them to the same type if necessary.

### Example

```js
console.log(5 == "5");
```

Output:

```txt
true
```

JavaScript converts `"5"` into `5` before comparing.

---

## Triple Equals (`===`)

The `===` operator checks whether both the value and the data type are the same.

### Example

```js
console.log(5 === "5");
```

Output:

```txt
false
```

The values look the same, but the types are different.

```txt
5      -> Number
"5"    -> String
```

---

# Comparing Numbers

```js
console.log(10 == 10);
console.log(10 === 10);
```

Output:

```txt
true
true
```

Both value and type are the same.

---

# Comparing Number and String

```js
console.log(10 == "10");
console.log(10 === "10");
```

Output:

```txt
true
false
```

Explanation:

```txt
==  → Converts "10" to 10
=== → No conversion
```

---

# Comparing Boolean Values

```js
console.log(true == 1);
console.log(true === 1);
```

Output:

```txt
true
false
```

With `==`, JavaScript converts:

```txt
true → 1
false → 0
```

---

# Comparing Null and Undefined

```js
console.log(null == undefined);
```

Output:

```txt
true
```

But:

```js
console.log(null === undefined);
```

Output:

```txt
false
```

Because their types are different.

---

# Empty String Comparison

```js
console.log("" == false);
```

Output:

```txt
true
```

JavaScript converts both values before comparison.

---

```js
console.log("" === false);
```

Output:

```txt
false
```

Different types:

```txt
""      → String
false   → Boolean
```

---

# Type Coercion

Type coercion means JavaScript automatically converts one data type into another.

Example:

```js
console.log("5" == 5);
```

Internally:

```txt
"5" → 5
5 == 5
```

Result:

```txt
true
```

This automatic conversion happens only with `==`.

---

# Why `===` Is Preferred

Using `===` makes comparisons predictable.

```js
const age = "18";

if (age === 18) {
  console.log("Adult");
}
```

Output:

```txt
Nothing prints
```

The types are different, so JavaScript does not perform any hidden conversion.

This helps avoid bugs.

---

# Real-World Example

### Using `==`

```js
const userId = "101";

if (userId == 101) {
  console.log("Matched");
}
```

Output:

```txt
Matched
```

The comparison succeeds because of type conversion.

---

### Using `===`

```js
const userId = "101";

if (userId === 101) {
  console.log("Matched");
}
```

Output:

```txt
Nothing prints
```

This behavior is safer because it prevents accidental matches.

---

# Best Practice

Always prefer:

```js
===  (Strict Equality)
!==  (Strict Inequality)
```

Instead of:

```js
==   (Loose Equality)
!=   (Loose Inequality)
```

---

# Key Points

- `==` compares values after type conversion.
- `===` compares both value and type.
- `==` can produce unexpected results because of type coercion.
- `===` is safer and more predictable.
- Modern JavaScript code should generally use `===`.
- Most style guides and companies recommend using `===` by default.
