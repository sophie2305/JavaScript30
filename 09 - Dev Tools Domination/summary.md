# Dev Tools Domination

## console

You can use `%c` to style the text you logged to the console.

``` javascript
console.log('%c This is blue by using percent c', 'color: blue');
```

You can also, log warning, errors and information to the console.

``` javascript
// warning!
console.warn('Warning');

// Error :|
console.error('ERROR!');

// Info
console.info('Crocodiles eat 3-4 people per year!');
```

Use `console.dir()` if you wish to see an interactive list of an elements properties and methods

``` javascript
console.dir(p);
```

You can use use assertions in the console, which will write an error message if the assertion is false. Nothing happens if the assertion is true.

``` javascript
const p = document.querySelector('p');
console.assert(p.classList.contains('ouch'), 'That is wrong!');
```

One useful feature for neatening the output on the console is `groupCollapsed`. It creates a new inline group until `groupEnd` is called.

``` javascript
dogs.forEach(dog => {
    console.groupCollapsed(`${dog.name}`);
    console.log(`This is ${dog.name}`);
    console.log(`${dog.name} is ${dog.age} years old`);
    console.groupEnd(`${dog.name}`);
});
```

Use `console.time()` to track how long an operation takes. Remember to give each timer a unique name and `use console.timeEnd()` with the same name to output the time in milliseconds since the timer was started

``` javascript
console.time('fetching data');
fetch('https://api.github.com/users/wesbos')
    .then(data => data.json())
    .then(data => {
    console.timeEnd('fetching data');
    console.log(data);
    })
```

The `console.count()` method logs the number of times that this particular call to `count()` has been called.
