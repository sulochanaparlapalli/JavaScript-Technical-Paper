# Array Utility Methods Chaining

## Definition

Method chaining is the practice of calling multiple methods one after another on the same value.

In JavaScript, array utility methods like `map()`, `filter()`, `reduce()`, `sort()`, and `find()` can be chained together to perform complex operations in a clean and readable way.

---

## Why Use Method Chaining?

Without chaining:

```js
const numbers = [1, 2, 3, 4, 5];

const evenNumbers = numbers.filter(num => num % 2 === 0);

const doubledNumbers = evenNumbers.map(num => num * 2);

console.log(doubledNumbers);
```

Output:

```txt
[4, 8]
```

---

## With Chaining

```js
const numbers = [1, 2, 3, 4, 5];

const result = numbers
  .filter(num => num % 2 === 0)
  .map(num => num * 2);

console.log(result);
```

Output:

```txt
[4, 8]
```

The result is the same, but the code is cleaner.

---

# How Chaining Works

Each method returns a value.

```txt
Array -> filter() -> New Array -> map() -> New Array -> reduce() -> Final Result
```

Because most array methods return a new array, another method can immediately be called on that result.

---

# Example 1: filter() + map()

```js
const numbers = [1, 2, 3, 4, 5, 6];

const result = numbers
  .filter(num => num % 2 === 0)
  .map(num => num * 10);

console.log(result);
```

Output:

```txt
[20, 40, 60]
```

---

# Example 2: filter() + map() + reduce()

```js
const numbers = [1, 2, 3, 4, 5, 6];

const result = numbers
  .filter(num => num % 2 === 0)
  .map(num => num * 10)
  .reduce((total, num) => total + num, 0);

console.log(result);
```

Output:

```txt
120
```

Explanation:

```txt
[1,2,3,4,5,6] filter -> [2,4,6] map -> [20,40,60] reduce -> 120
```

---

# Example 3: Working with Objects

```js
const users = [
  { name: "John", age: 25 },
  { name: "Sara", age: 17 },
  { name: "Mike", age: 30 }
];

const result = users
  .filter(user => user.age >= 18)
  .map(user => user.name);

console.log(result);
```

Output:

```txt
["John", "Mike"]
```

---

# Example 4: sort() + map()

```js
const numbers = [5, 2, 8, 1];

const result = numbers
  .sort((a, b) => a - b)
  .map(num => num * 2);

console.log(result);
```

Output:

```txt
[2, 4, 10, 16]
```

---

## Important Note

`sort()` modifies the original array.

```js
const numbers = [5, 2, 8, 1];

numbers.sort();

console.log(numbers);
```

Output:

```txt
[1, 2, 5, 8]
```

Unlike `map()` and `filter()`, `sort()` is mutable.

---

# Example 5: find()

```js
const users = [
  { name: "John", age: 20 },
  { name: "Sara", age: 30 },
  { name: "Mike", age: 25 }
];

const result = users
  .filter(user => user.age >= 25)
  .find(user => user.name.startsWith("M"));

console.log(result);
```

Output:

```txt
{ name: "Mike", age: 25 }
```

---

# Example 6: Real-World Product Example

```js
const products = [
  { name: "Laptop", price: 50000, inStock: true },
  { name: "Phone", price: 25000, inStock: false },
  { name: "Tablet", price: 30000, inStock: true }
];

const result = products
  .filter(product => product.inStock)
  .map(product => product.name);

console.log(result);
```

Output:

```txt
["Laptop", "Tablet"]
```

---

# Common Chaining Pattern

```js
array
  .filter(...)
  .map(...)
  .sort(...)
  .reduce(...)
```

This is one of the most common patterns in modern JavaScript.

---

# Methods Commonly Used in Chaining

### Filtering

```js
filter()
```

---

### Transformation

```js
map()
flatMap()
```

---

### Searching

```js
find()
findIndex()
```

---

### Aggregation

```js
reduce()
```

---

### Sorting

```js
sort()
```

---

### Checking Conditions

```js
every()
some()
```

---

# Common Mistake

### Forgetting That reduce() Ends the Chain

```js
const result = numbers
  .map(num => num * 2)
  .reduce((sum, num) => sum + num, 0);
```

After `reduce()`, the result is usually not an array.

Trying to continue:

```js
numbers
  .map(num => num * 2)
  .reduce((sum, num) => sum + num, 0)
  .filter(num => num > 10);
```

Output:

```txt
TypeError
```

Because `reduce()` returns a number.

---

# Benefits of Method Chaining

- Less code.
- Cleaner syntax.
- Easier to read.
- Reduces temporary variables.
- Encourages functional programming.
- Common in React and modern JavaScript applications.

---

# Real Interview Example

```js
const numbers = [1, 2, 3, 4, 5, 6];

const result = numbers
  .filter(num => num % 2 === 0)
  .map(num => num * num)
  .reduce((sum, num) => sum + num, 0);

console.log(result);
```

Output:

```txt
56
```

Calculation:

```txt
[2,4,6] -> [4,16,36] -> 56
```

---

# Key Points

- Method chaining means calling multiple methods in sequence.
- Most array utility methods return a new array.
- `map()` and `filter()` are commonly chained.
- `reduce()` usually ends a chain because it returns a single value.
- `sort()` modifies the original array.
- Chaining produces cleaner and more readable code.
- Chaining is heavily used in modern JavaScript development.
