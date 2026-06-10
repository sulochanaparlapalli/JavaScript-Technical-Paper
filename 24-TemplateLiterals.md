# Template Literals

## Definition

Template literals are a modern way to create strings in JavaScript using backticks (`` ` ``) instead of single quotes (`'`) or double quotes (`"`).

They provide powerful features such as:

- String interpolation
- Multi-line strings
- Embedded expressions
- Tagged templates
- Easier string formatting

Template literals were introduced in ES6 (ECMAScript 2015).

---

## Syntax

```js
const message = `Hello World`;
```

Unlike normal strings, template literals use backticks.

---

## Why Template Literals?

Before template literals, developers had to use string concatenation.

### Old Way

```js
const name = "John";

console.log("Hello " + name);
```

Output:

```txt
Hello John
```

This becomes difficult to read when multiple variables are involved.

---

## Template Literal Way

```js
const name = "John";

console.log(`Hello ${name}`);
```

Output:

```txt
Hello John
```

The `${}` syntax is called **interpolation**.

---

## String Interpolation

Interpolation allows variables to be inserted directly into a string.

```js
const firstName = "John";
const lastName = "Doe";

console.log(`Full Name: ${firstName} ${lastName}`);
```

Output:

```txt
Full Name: John Doe
```

---

## Embedding Expressions

Anything that returns a value can be placed inside `${}`.

```js
const a = 10;
const b = 20;

console.log(`Sum: ${a + b}`);
```

Output:

```txt
Sum: 30
```

More examples:

```js
console.log(`Multiplication: ${5 * 4}`);
console.log(`Random Number: ${Math.random()}`);
```

---

## Calling Functions Inside Template Literals

```js
function greet(name) {
  return `Hello ${name}`;
}

console.log(`${greet("John")}!`);
```

Output:

```txt
Hello John!
```

---

## Using Conditional Expressions

```js
const age = 20;

console.log(`Status: ${age >= 18 ? "Adult" : "Minor"}`);
```

Output:

```txt
Status: Adult
```

---

## Multi-line Strings

One of the biggest advantages of template literals is multi-line text.

### Old Way

```js
const text =
  "Hello\n" +
  "World\n" +
  "JavaScript";
```

### Template Literal Way

```js
const text = `
Hello
World
JavaScript
`;

console.log(text);
```

Output:

```txt
Hello
World
JavaScript
```

No need for `\n`.

---

## Creating HTML Templates

```js
const user = "John";

const html = `
<div>
  <h1>Welcome ${user}</h1>
</div>
`;

console.log(html);
```

Output:

```html
<div>
  <h1>Welcome John</h1>
</div>
```

---

## Building Dynamic Messages

```js
const product = "Laptop";
const price = 50000;

console.log(`The ${product} costs ₹${price}.`);
```

Output:

```txt
The Laptop costs ₹50000.
```

---

## Nested Template Literals

```js
const isLoggedIn = true;

const message = `User Status: ${
  isLoggedIn ? `Logged In` : `Logged Out`
}`;

console.log(message);
```

Output:

```txt
User Status: Logged In
```

---

## Tagged Template Literals (Advanced)

A tagged template literal allows a function to process a template literal.

```js
function tag(strings, value) {
  return strings[0] + value.toUpperCase();
}

const result = tag`Hello ${"world"}`;

console.log(result);
```

Output:

```txt
Hello WORLD
```

---

## Real-World Example

```js
const employee = {
  name: "John",
  role: "Developer",
  salary: 60000
};

console.log(`
Employee Details
----------------
Name: ${employee.name}
Role: ${employee.role}
Salary: ₹${employee.salary}
`);
```

Output:

```txt
Employee Details
----------------
Name: John
Role: Developer
Salary: ₹60000
```

---

## Common Mistakes

### Using Quotes Instead of Backticks

❌ Wrong

```js
const name = "John";

console.log("Hello ${name}");
```

Output:

```txt
Hello ${name}
```

### Correct

```js
console.log(`Hello ${name}`);
```

Output:

```txt
Hello John
```

---

## Template Literals vs String Concatenation

### String Concatenation

```js
const name = "John";
const age = 25;

console.log("My name is " + name + " and I am " + age + " years old.");
```

### Template Literals

```js
const name = "John";
const age = 25;

console.log(`My name is ${name} and I am ${age} years old.`);
```

Template literals are cleaner and easier to read.

---

## Key Points

- Template literals use backticks (`` ` ``).
- `${}` is used for interpolation.
- Variables can be inserted directly into strings.
- Expressions and function calls can be embedded.
- Multi-line strings are supported without `\n`.
- Tagged templates provide advanced customization.
- Widely used in modern JavaScript applications.
- Introduced in ES6 (ECMAScript 2015).
