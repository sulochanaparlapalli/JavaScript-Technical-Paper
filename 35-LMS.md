# JavaScript Best Practices

## Definition

Best practices are guidelines that help developers write clean, readable, maintainable, and bug-free code.

Following best practices makes code easier to understand for both you and other developers.

---

# 1. Use Consistent Indentation

Indent code properly to improve readability.

### Bad

```js
function greet() {
console.log("Hello");
if (true) {
console.log("Welcome");
}
}
```

---

### Good

```js
function greet() {
  console.log("Hello");

  if (true) {
    console.log("Welcome");
  }
}
```

---

## Recommended

- Use 2 or 4 spaces consistently.
- Do not mix tabs and spaces.

---

# 2. Use Meaningful Variable Names

Variable names should describe their purpose.

### Bad

```js
const x = 25;
const y = "John";
```

---

### Good

```js
const age = 25;
const userName = "John";
```

---

# 3. Follow camelCase Naming

JavaScript variables and functions typically use camelCase.

### Bad

```js
const user_name = "John";
const USER_NAME = "John";
```

---

### Good

```js
const userName = "John";
```

---

# 4. Use Descriptive Function Names

Functions should describe what they do.

### Bad

```js
function data() {}
```

---

### Good

```js
function fetchUserData() {}
```

---

# 5. Use Meaningful Loop Variable Names

For small loops:

```js
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

`i`, `j`, and `k` are acceptable.

---

For arrays and objects:

### Bad

```js
users.forEach(x => {
  console.log(x.name);
});
```

---

### Good

```js
users.forEach(user => {
  console.log(user.name);
});
```

---

# 6. Prefer const Over let

Use `const` unless the value changes.

### Good

```js
const userName = "John";
```

---

Use `let` only when reassignment is needed.

```js
let count = 0;

count++;
```

---

Avoid:

```js
var count = 0;
```

---

# 7. Avoid var

### Problems with var

- Function scoped
- Hoisting confusion
- Can cause bugs

### Prefer

```js
const
let
```

---

# 8. Use Strict Equality

### Bad

```js
if (age == "18") {
}
```

---

### Good

```js
if (age === 18) {
}
```

Strict equality avoids unexpected type coercion.

---

# 9. Write Small Functions

### Bad

```js
function processEverything() {
  // 200 lines
}
```

---

### Good

```js
function validateUser() {}

function saveUser() {}

function sendEmail() {}
```

Small functions are easier to test and maintain.

---

# 10. Avoid Deep Nesting

### Bad

```js
if (user) {
  if (user.isAdmin) {
    if (user.isActive) {
      console.log("Access Granted");
    }
  }
}
```

---

### Good

```js
if (!user) return;

if (!user.isAdmin) return;

if (!user.isActive) return;

console.log("Access Granted");
```

---

# 11. Use Template Literals

### Bad

```js
const message = "Hello " + name;
```

---

### Good

```js
const message = `Hello ${name}`;
```

Cleaner and easier to read.

---

# 12. Use Destructuring

### Bad

```js
const name = user.name;
const age = user.age;
```

---

### Good

```js
const { name, age } = user;
```

---

# 13. Keep Functions Pure When Possible

A pure function:

- Depends only on inputs.
- Returns the same output for the same input.

```js
function add(a, b) {
  return a + b;
}
```

---

Avoid unnecessary side effects.

---

# 14. Use Array Methods Instead of Loops When Appropriate

### Traditional Loop

```js
const doubled = [];

for (let i = 0; i < numbers.length; i++) {
  doubled.push(numbers[i] * 2);
}
```

---

### Better

```js
const doubled = numbers.map(num => num * 2);
```

---

# 15. Handle Errors Properly

### Bad

```js
JSON.parse(data);
```

---

### Good

```js
try {
  JSON.parse(data);
} catch (error) {
  console.error(error.message);
}
```

---

# 16. Use Early Returns

### Bad

```js
function login(user) {
  if (user) {
    console.log("Logged In");
  }
}
```

---

### Good

```js
function login(user) {
  if (!user) return;

  console.log("Logged In");
}
```

---

# 17. Comment Why, Not What

### Bad

```js
// Increment count
count++;
```

---

### Good

```js
// Retry counter for failed API requests
count++;
```

Comments should explain reasoning.

---

# 18. Use Meaningful Boolean Names

### Bad

```js
const flag = true;
```

---

### Good

```js
const isLoggedIn = true;
const hasPermission = true;
const canEdit = false;
```

---

# 19. Avoid Global Variables

### Bad

```js
let count = 0;
```

Global variables can be modified from anywhere.

---

### Better

```js
function counter() {
  let count = 0;
}
```

Keep variables in the smallest scope possible.

---

# 20. Use Default Parameters

### Bad

```js
function greet(name) {
  name = name || "Guest";
}
```

---

### Good

```js
function greet(name = "Guest") {
}
```

---

# 21. Consistent Braces

### Bad

```js
if (isAdmin)
  console.log("Admin");
```

---

### Good

```js
if (isAdmin) {
  console.log("Admin");
}
```

Always use braces for clarity.

---

# 22. Use Proper File Names

### Good Examples

```txt
userService.js
authController.js
fileUtils.js
```

---

### Avoid

```txt
abc.js
test1.js
newfile.js
```

File names should describe their purpose.

---

# Key Points

- Code is read more often than it is written.
- Consistent formatting improves readability.
- Use descriptive names for variables and functions.
- Prefer `const` and `let` over `var`.
- Use strict equality (`===`).
- Keep functions small and focused.
- Avoid deep nesting and global variables.
- Organize code into modules.
- Remove unused code regularly.
- Write code that other developers can easily understand.
