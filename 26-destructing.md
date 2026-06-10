# Destructuring

## Definition

Destructuring is a JavaScript feature that allows you to extract values from arrays or properties from objects and store them in variables.

It provides a shorter and cleaner way to work with data.

Destructuring was introduced in ES6 (ECMAScript 2015).

---

## Why Use Destructuring?

Without destructuring, accessing values can become repetitive.

### Without Destructuring

```js
const person = {
  name: "John",
  age: 25
};

const name = person.name;
const age = person.age;

console.log(name);
console.log(age);
```

Output:

```txt
John
25
```

---

## Object Destructuring

### Basic Example

```js
const person = {
  name: "John",
  age: 25
};

const { name, age } = person;

console.log(name);
console.log(age);
```

Output:

```txt
John
25
```

---

## Variable Names Must Match Property Names

```js
const user = {
  username: "john123",
  city: "Bangalore"
};

const { username, city } = user;

console.log(username);
console.log(city);
```

Output:

```txt
john123
Bangalore
```

---

## Renaming Variables

You can assign properties to different variable names.

```js
const person = {
  name: "John",
  age: 25
};

const { name: fullName, age: userAge } = person;

console.log(fullName);
console.log(userAge);
```

Output:

```txt
John
25
```

---

## Default Values

If a property does not exist, a default value can be provided.

```js
const user = {
  name: "John"
};

const { name, country = "India" } = user;

console.log(name);
console.log(country);
```

Output:

```txt
John
India
```

---

## Array Destructuring

### Basic Example

```js
const colors = ["Red", "Green", "Blue"];

const [first, second, third] = colors;

console.log(first);
console.log(second);
console.log(third);
```

Output:

```txt
Red
Green
Blue
```

---

## Skipping Elements

```js
const numbers = [10, 20, 30, 40];

const [first, , third] = numbers;

console.log(first);
console.log(third);
```

Output:

```txt
10
30
```

---

## Using Default Values with Arrays

```js
const numbers = [10];

const [a, b = 20] = numbers;

console.log(a);
console.log(b);
```

Output:

```txt
10
20
```

---

## Swapping Variables

Before destructuring:

```js
let a = 10;
let b = 20;

let temp = a;
a = b;
b = temp;
```

With destructuring:

```js
let a = 10;
let b = 20;

[a, b] = [b, a];

console.log(a);
console.log(b);
```

Output:

```txt
20
10
```

---

## Rest Operator with Destructuring

### Arrays

```js
const numbers = [1, 2, 3, 4, 5];

const [first, ...remaining] = numbers;

console.log(first);
console.log(remaining);
```

Output:

```txt
1
[2, 3, 4, 5]
```

---

### Objects

```js
const user = {
  name: "John",
  age: 25,
  city: "Bangalore"
};

const { name, ...others } = user;

console.log(name);
console.log(others);
```

Output:

```txt
John
{ age: 25, city: "Bangalore" }
```

---

## Nested Object Destructuring

```js
const user = {
  name: "John",
  address: {
    city: "Bangalore",
    state: "Karnataka"
  }
};

const {
  address: { city, state }
} = user;

console.log(city);
console.log(state);
```

Output:

```txt
Bangalore
Karnataka
```

---

## Destructuring Function Parameters

Without destructuring:

```js
function printUser(user) {
  console.log(user.name);
  console.log(user.age);
}
```

With destructuring:

```js
function printUser({ name, age }) {
  console.log(name);
  console.log(age);
}

printUser({
  name: "John",
  age: 25
});
```

Output:

```txt
John
25
```

---

## Real-World Example

```js
const employee = {
  id: 101,
  name: "John",
  role: "Developer",
  salary: 60000
};

const { name, role } = employee;

console.log(`${name} works as a ${role}`);
```

Output:

```txt
John works as a Developer
```

---

## Common Mistakes

### Property Does Not Exist

```js
const user = {
  name: "John"
};

const { age } = user;

console.log(age);
```

Output:

```txt
undefined
```

---

### Forgetting Curly Braces for Objects

Wrong

```js
const name, age = person;
```

Correct

```js
const { name, age } = person;
```

---

## Key Points

- Destructuring extracts values from arrays and objects.
- Introduced in ES6.
- Supports default values.
- Supports renaming variables.
- Supports nested objects.
- Supports the rest operator (`...`).
- Useful for function parameters.
- Commonly used in modern JavaScript applications and frameworks.
