# Array Cardio Day 2

## Array.prototype.some()

Checks against the array and returns `true` if at least one item meets the condition specified.

```javascript
const isAdult = people.some(
  (person) => new Date().getFullYear() - person.year >= 19
);
```

- `new Date()).getFullYear()` gets the current year

## Array.prototype.every()

Checks against the array and returns `true` if all items meets the condition specified.

```javascript
const allAdults = people.every(
  (person) => new Date().getFullYear() - person.year >= 19
);
```

## Array.prototype.find()

Checks against the array and returns the result of the item that meets the criteria

```javascript
const index = comments.find((comment) => (comment) => comment.id === 823423);
```

## Array.prototype.findIndex()

Checks against the array and returns the `index` of the item that meets the condition specified.

```javascript
const index = comments.findIndex((comment) => comment.id === 823423);
```

- `splice` can be used to remove the element using the index from the array, but this will change the original object

```javascript
comments.splice(index, 1);
```

- Use the `spread` syntax along with `slice` to create a new array with the specified index removed. This keeps the original array intact.

```javascript
const newComments = [...comments.slice(0, index), ...comments.slice(index + 1)];
```
