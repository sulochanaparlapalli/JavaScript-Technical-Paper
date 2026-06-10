# Spread Operator (`...`)

## Definition

The **spread operator** (`...`) is used to expand or unpack elements from an array, object, or iterable into individual elements.

It makes copying, merging, and passing data much easier.

---

## Syntax

```js
...value
```

---

# 1. Spread Operator with Arrays

## Example

```js
const numbers = [1, 2, 3];

console.log(...numbers);
```

Output:

```txt
1 2 3
```

The array elements are spread into individual values.

---

# 2. Copying an Array

## Without Spread Operator

```js
const arr1 = [1, 2, 3];
const arr2 = arr1;

arr2.push(4);

console.log(arr1);
```

Output:

```txt
[1, 2, 3, 4]
```

Both variables reference the same array.

---

## With Spread Operator

```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1];

arr2.push(4);

console.log(arr1);
console.log(arr2);
```

Output:

```txt
[1, 2, 3]
[1, 2, 3, 4]
```

A new array is created.

---

# 3. Merging Arrays

## Example

```js
const frontend = ["HTML", "CSS"];
const backend = ["Node.js", "MongoDB"];

const skills = [...frontend, ...backend];

console.log(skills);
```

Output:

```txt
["HTML", "CSS", "Node.js", "MongoDB"]
```

---

# 4. Adding New Elements

## Example

```js
const numbers = [2, 3, 4];

const updated = [1, ...numbers, 5];

console.log(updated);
```

Output:

```txt
[1, 2, 3, 4, 5]
```

---

# 5. Spread Operator with Objects

## Example

```js
const user = {
  name: "John",
  age: 25
};

const copiedUser = {
  ...user
};

console.log(copiedUser);
```

Output:

```txt
{ name: "John", age: 25 }
```

---

# 6. Merging Objects

## Example

```js
const personalInfo = {
  name: "John"
};

const contactInfo = {
  email: "john@example.com"
};

const user = {
  ...personalInfo,
  ...contactInfo
};

console.log(user);
```

Output:

```txt
{
  name: "John",
  email: "john@example.com"
}
```

---

# 7. Updating Object Properties

## Example

```js
const user = {
  name: "John",
  age: 25
};

const updatedUser = {
  ...user,
  age: 26
};

console.log(updatedUser);
```

Output:

```txt
{
  name: "John",
  age: 26
}
```

---

# 8. Passing Array Values as Function Arguments

## Example

```js
function add(a, b, c) {
  return a + b + c;
}

const numbers = [10, 20, 30];

console.log(add(...numbers));
```

Output:

```txt
60
```

Without spread:

```js
add(numbers);
```

This would not work correctly.

---

# 9. Converting Strings to Arrays

## Example

```js
const word = "JavaScript";

const letters = [...word];

console.log(letters);
```

Output:

```txt
["J", "a", "v", "a", "S", "c", "r", "i", "p", "t"]
```

---

# 10. Finding Maximum Value

## Example

```js
const numbers = [10, 20, 30, 40];

console.log(Math.max(...numbers));
```

Output:

```txt
40
```

Without spread:

```js
Math.max(numbers);
```

Output:

```txt
NaN
```

---

# Spread Operator vs Rest Operator

Although both use `...`, they serve different purposes.

## Spread Operator

Expands values.

```js
const numbers = [1, 2, 3];

console.log(...numbers);
```

Output:

```txt
1 2 3
```

---

## Rest Operator

Collects values.

```js
function sum(...numbers) {
  console.log(numbers);
}

sum(1, 2, 3);
```

Output:

```txt
[1, 2, 3]
```

---

# Common Real-World Example

```js
const existingUsers = ["John", "Alice"];

const newUsers = [
  ...existingUsers,
  "Bob"
];

console.log(newUsers);
```

Output:

```txt
["John", "Alice", "Bob"]
```

---

# Key Benefits

- Creates copies of arrays and objects.
- Merges arrays easily.
- Merges objects easily.
- Adds elements without modifying originals.
- Passes array values as function arguments.
- Makes code shorter and cleaner.
- Widely used in React and modern JavaScript.
