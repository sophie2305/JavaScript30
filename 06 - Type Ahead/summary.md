# Type Ahead

- `change` & `keyup` events
- Promise: `fetch()`, `then()`, `json()`
- Array: `filter()`, `map()`, `push()`, `join()`
- Regexp: `match()`, `replace()`

## `change` & `keyup` events

`change` can also be an event in `addEventListener` for inputs, but the `change` only fires when we step outside that input. so we need to tie the element up with the `keyup` event as well for better user experience.

```JavaScript
searchInput.addEventListener('change', displayMatches);
searchInput.addEventListener('keyup', displayMatches);
```

## Fetch API

[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) provides an interface for fetching resources(including across the network). It will seem familiar to anyone who has used [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest), but the new API provides a more powerful and flexible feature set.

[fetch()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch) is one of GlobalFetch API method used to start the process of fetching a resource.

```JavaScript
fetch(input, init).then(function(response) {...});
```

in [MDN's basic fetch example](https://developer.mozilla.org/en-US/docs/Web/API/GlobalFetch)(see `Examples` section) like:

```JavaScript
var myImage = document.querySelector('.my-image');

fetch('flowers.jpg')
  .then(function(response) {
    if (!response.ok) return new Error(response);
    return response.blob();
  })
  .then(function(myBlob) {
    var objectURL = URL.createObjectURL(myBlob);
    myImage.src = objectURL;
  })
```

in ES6 syntax will be like:

```JavaScript
const myImage = document.querySelector('img');

fetch('flowers.jpg')
  .then(response => response.blob())
  .then(myBlob => {
    const objectURL = URL.createObjectURL(myblob);
    myImage.src = objectURL;
  });
```

above example shows using `blob()` to fetch image. There are many other ways as well. We use `json()` in this case.


### ES6 Spread syntax

[Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator) allows an expression to be expanded in places where multiple arguments(for function calls) or multiple elements(for array literals) or multiple variables(for destructing assignment) are expected.

For function calls:

```JavaScript
myFunction(...iterableObj);
```

For array literals:

```JavaScript
[...iterableObj, 4, 5, 6]
```

usually, we use [`Function.prototype.apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) in cases like:

```JavaScript
function myFunction(x, y, z) {}
var args = [0, 1, 2];
myFunction.apply(null, args);
```

but in ES6 we can now write the above as:

```JavaScript
function myFunction(x, y, z) {}
var args = [0, 1, 2];
myFunction(...args);
```

### RegExp

[You construct a regular expression in one of two ways](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions):

- Using a regular expression literal, which consists of a pattern enclosed between slashes, as follows:

```JavaScript
let re = /ab+c/;
```
Regular expression literals provide compilation of the regular expression when the script is loaded. If the regular expression remains constant, using this can improve performance.

- Or calling the constructor function of the RegExp object, as follows:
```JavaScript
let re = new RegExp('ab+c');
```
Using the constructor function provides runtime compilation of the regular expression. Use the constructor function when you know the regular expression pattern will be changing, or you don't know the pattern and are getting it from another source, such as user input.

Regular expressions have six optional flags that allow for functionality like global and case insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.

To include a flag with the regular expression, use this syntax:
```JavaScript
var re = /pattern/flags;
```
or
```JavaScript
var re = new RegExp('pattern', 'flags');
```

## Tasks

- [ ] - Sort the suggestions list by geolocation