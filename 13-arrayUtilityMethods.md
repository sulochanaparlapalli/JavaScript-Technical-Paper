# Popular Array Utility Methods

## Definition

Array utility methods help manipulate, transform, search, and process arrays efficiently.

- Mutable methods → modify the original array
- Immutable methods → return a new array (original stays unchanged)

---

## 1. Basics

## `push()` **(Mutable)**

- **Description**: Adds one or more elements to the end of the array.
- **Returns**: The new length of the array.

```js
const arr = [1, 2, 3];
arr.push(4, 5);
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `pop()` **(Mutable)**

- **Description**: Removes the last element from the array.
- **Returns**: The removed element.

```js
const arr = [1, 2, 3, 4];
const popped = arr.pop();
console.log(popped); // 4
console.log(arr); // [1, 2, 3]
```

---

## `slice()` **(Immutable)**

- **Description**: Returns a shallow copy of a portion of the array.
- **Returns**: A new array containing the sliced elements.

```js
const arr = [1, 2, 3, 4, 5];
const sliced = arr.slice(1, 4);
console.log(sliced); // [2, 3, 4]
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `splice()` **(Mutable)**

- **Description**: Adds/removes elements from the array.
- **Returns**: The removed elements (if any).

```js
const arr = [1, 2, 3, 4, 5];
const spliced = arr.splice(1, 2, 'a', 'b'); // removes 2 elements from index 1 and adds 'a' and 'b'
console.log(spliced); // [2, 3]
console.log(arr); // [1, 'a', 'b', 4, 5]
```

---

## `join()` **(Immutable)** 

- **Description**: Joins all elements of the array into a string.
- **Returns**: The joined string.

```js
const arr = ['a', 'b', 'c'];
const joined = arr.join('-');
console.log(joined); // 'a-b-c'
console.log(arr); // ['a', 'b', 'c']
```

---

## `flat()` **(Immutable)**

- **Description**: Flattens a nested array into a single-level array.
- **Returns**: A new, flattened array.

```js
const arr = [1, [2, 3], [4, 5]];
const flattened = arr.flat();
console.log(flattened); // [1, 2, 3, 4, 5]
console.log(arr); // [1, [2, 3], [4, 5]]
```

---

## `concat()` **(Immutable)**

- **Description**: Concatenates two or more arrays.
- **Returns**: A new array containing the concatenated elements.

```js
const arr1 = [1, 2];
const arr2 = [3, 4];
const concatenated = arr1.concat(arr2);
console.log(concatenated); // [1, 2, 3, 4]
console.log(arr1); // [1, 2]
console.log(arr2); // [3, 4]
```

---

## 2. Finding Methods

## `find()` **(Immutable)**

- **Description**: Returns the first element that satisfies the provided testing function.
- **Returns**: The found element, or `undefined` if no element satisfies the function.

```js
const arr = [1, 2, 3, 4, 5];
const found = arr.find((num) => num > 3);
console.log(found); // 4
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `findIndex()` **(Immutable)**

- **Description**: Returns the index of the first element that satisfies the provided testing function.
- **Returns**: The index of the found element, or `-1` if no element satisfies the function.

```js
const arr = [1, 2, 3, 4, 5];
const index = arr.findIndex((num) => num > 3);
console.log(index); // 3
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `indexOf()` **(Immutable)**

- **Description**: Returns the index of the first occurrence of a specified element in the array.
- **Returns**: The index of the found element, or `-1` if the element is not found.

```js
const arr = [1, 2, 3, 4, 5];
const index = arr.indexOf(3);
console.log(index); // 2
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `includes()` **(Immutable)** 

- **Description**: Returns `true` if the array includes a specified element, `false` otherwise.
- **Returns**: `true` or `false`.

```js
const arr = [1, 2, 3, 4, 5];
const result = arr.includes(3);
console.log(result); // true
console.log(arr); // [1, 2, 3, 4, 5]
```

----

## 3. Higher Order Functions

## `forEach()` **(Immutable)**

- **Description**: Executes a provided function once for each array element.
- **Returns**: `undefined`.

```js
const arr = [1, 2, 3, 4, 5];
arr.forEach((num) => console.log(num));
```

---

## `map()` **(Immutable)**

- **Description**: Creates a new array with the results of calling a provided function on every element in the calling array.
- **Returns**: A new array with the same length as the original array.

```js
const arr = [1, 2, 3, 4, 5];
const doubled = arr.map((num) => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `filter()` **(Immutable)**

- **Description**: Creates a new array with all elements that pass the test implemented by the provided function.
- **Returns**: A new array with the filtered elements.

```js
const arr = [1, 2, 3, 4, 5];
const even = arr.filter((num) => num % 2 === 0);
console.log(even); // [2, 4]
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `reduce()` **(Immutable)**

- **Description**: Executes a reducer function on each element of the array, resulting in a single output value.
- **Returns**: The accumulated value.

```js
const arr = [1, 2, 3, 4, 5];
const sum = arr.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## `sort()` **(Mutable)**

- **Description**: Sorts the elements of an array in place and returns the sorted array.
- **Returns**: The sorted array.

```js
const arr = [5, 3, 1, 4, 2];
const sorted = arr.sort((a, b) => a - b);
console.log(sorted); // [1, 2, 3, 4, 5]
console.log(arr); // [1, 2, 3, 4, 5]
```

---

## 4. Advanced

## Method Chaining (Immutable style)

```js
const arr = [1, 2, 3, 4, 5];
const result = arr
  .map((num) => num * 2)
  .filter((num) => num % 2 === 0)
  .reduce((acc, num) => acc + num, 0);
console.log(result); // 30
```

---

## Mutable Methods (modify original)

- push
- pop
- splice
- sort

---

## Immutable Methods (return new data)

- concat
- slice
- map
- filter
- reduce
- find
- findIndex
- includes
- indexOf
- join
- flat

---

## Special

- forEach → no return, just iteration
