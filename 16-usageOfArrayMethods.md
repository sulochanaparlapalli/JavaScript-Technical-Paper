# When to Use forEach, map, filter, reduce

## forEach()

Used when performing an action for every element.

```js
const numbers = [1, 2, 3];

numbers.forEach(num => console.log(num));
```

Output:

```
1
2
3
```

---

## map()

Used when creating a transformed array.

```js
const numbers = [1, 2, 3];

const squared = numbers.map(num => num * num);
```

Output:

```
1
4
9
```

---

## filter()

Used when selecting elements.

```js
const numbers = [10, 20, 30];

const result = numbers.filter(num => num > 15);
```

Output:

```
20
30
```

---

## reduce()

Used when generating one final value.

```js
const numbers = [1, 2, 3];

const total = numbers.reduce((sum, num) => sum + num, 0);
```

Output:

```
6
```

---

## Key Points

| Method | Purpose |
|----------|----------|
| forEach | Iterate |
| map | Transform |
| filter | Select |
| reduce | Aggregate |
