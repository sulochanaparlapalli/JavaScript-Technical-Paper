# Popular String Utility Methods in JavaScript

## Definition

String methods help us manipulate, search, extract, and modify text.

Strings are **immutable** in JavaScript.

This means string methods do not modify the original string. Instead, they return a new string.

--- 

Example:

```js
let name = "john";

let upperName = name.toUpperCase();

console.log(name);

console.log(upperName); 
```

Output:

```txt
john
JOHN
```

The original string remains unchanged.

---

# Case Conversion Methods

## String.toUpperCase()

Converts all characters to uppercase.

### Syntax

```js
string.toUpperCase();
```

### Example

```js
const name = "john";

console.log(name.toUpperCase());
```

Output:

```txt
JOHN
```

---

## String.toLowerCase()

Converts all characters to lowercase.

### Syntax

```js
string.toLowerCase();
```

### Example

```js
const city = "BANGALORE";

console.log(city.toLowerCase());
```

Output:

```txt
bangalore
```

---

# Removing Spaces

## String.trim()

Removes spaces from both ends.

### Syntax

```js
string.trim();
```

### Example

```js
const text = "   Hello World   ";

console.log(text.trim());
```

Output:

```txt
Hello World
```

---

# Searching Methods

## String.includes()

Checks if a substring exists.

### Syntax

```js
string.includes(value);
```

### Example

```js
const text = "I love JavaScript";

console.log(text.includes("JavaScript"));
```

Output:

```txt
true
```

---

## String.startsWith()

Checks whether a string starts with specific text.

### Syntax

```js
string.startsWith(value);
```

### Example

```js
const text = "JavaScript";

console.log(text.startsWith("Java"));
```

Output:

```txt
true
```

---

## String.endsWith()

Checks whether a string ends with specific text.

### Syntax

```js
string.endsWith(value);
```

### Example

```js
const text = "JavaScript";

console.log(text.endsWith("Script"));
```

Output:

```txt
true
```

---

## String.indexOf()

Returns position of first match (or -1 if not found).

### Syntax

```js
string.indexOf(value);
```

### Example

```js
const text = "JavaScript";

console.log(text.indexOf("S"));
```

Output:

```txt
4
```

---

# Extracting Methods

## String.slice()

Extracts part of a string.

### Syntax

```js
string.slice(start, end);
```

### Example

```js
const text = "JavaScript";

console.log(text.slice(0, 4));
```

Output:

```txt
Java
```

Supports negative indexing

```js
const text = "JavaScript";

console.log(text.slice(-6));
```

Output:

```txt
Script
```

---

## String.substring()

Returns part of a string.

### Syntax

```js
string.substring(start, end);
```

### Example

```js
const text = "JavaScript";

console.log(text.substring(4, 10));
```

Output:

```txt
Script
```

`substring()` does NOT support negative indexes

```js
const text = "JavaScript";

console.log(text.substring(-6));

console.log(text.substring(-6, -2));
```

Output:

```txt
JavaScript

(no output)
```


---

# Replacing Text

## String.replace()

Replaces the first occurrence.

### Syntax

```js
string.replace(oldValue, newValue);
```

### Example

```js
const text = "I love Java";

console.log(
  text.replace("Java", "JavaScript")
);
```

Output:

```txt
I love JavaScript
```

---

## String.replaceAll()

Replaces all occurrences.

### Syntax

```js
string.replaceAll(oldValue, newValue);
```

### Example

```js
const text = "cat cat cat";

console.log(
  text.replaceAll("cat", "dog")
);
```

Output:

```txt
dog dog dog
```

---

# Splitting Strings

## String.split()

Converts a string into an array.

### Syntax

```js
string.split(separator);
```

### Example

```js
const fruits = "apple,banana,mango";

console.log(
  fruits.split(",")
);
```

Output:

```txt
["apple", "banana", "mango"]
```

---

# Character Access

## String.charAt()

Returns a character at a position.

### Syntax

```js
string.charAt(index);
```

### Example

```js
const text = "JavaScript";

console.log(text.charAt(0));
```

Output:

```txt
J
```

---

# Length Property

## String.length

Returns total characters.

### Syntax

```js
string.length
```

### Example

```js
const text = "JavaScript";

console.log(text.length);
```

Output:

```txt
10
```

---

# Repeat Strings

## String.repeat()

Repeats a string.

### Syntax

```js
string.repeat(count);
```

### Example

```js
const text = "Hi ";

console.log(text.repeat(3));
```

Output:

```txt
Hi Hi Hi
```

---

## Key Points

- Strings are immutable.
- String methods return new strings.
- No method modifies original string.
- Very useful for data cleaning, searching, and formatting.
