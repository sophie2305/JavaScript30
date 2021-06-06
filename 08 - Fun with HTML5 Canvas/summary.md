# Fun with HTML5 Canvas

## getContext

The canvas has properties that can be modified to alter the line style.

``` javascript
const ctx = canvas.getContext('2d');

ctx.strokeStyle = '#BADA55';
ctx.lineJoin = 'round';
ctx.lineCap = 'round';
ctx.lineWidth = 10;
```

## Destructuring assignment

ES6 allows you to easily name multiple variables, demonstrated by the the following code

``` javascript
[lastX, lastY] = [event.offsetX, event.offsetY];
```