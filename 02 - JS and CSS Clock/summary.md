# JS and CSS Clock Notes

What I learned on this mini-project.

## Date object

You can extract the `second`, `minute` and `hour` of the date object by accessing it's object methods.

```javascript
const seconds = now.getSeconds();
const minutes = now.getMinutes();
const hours = now.getHours();
```

## setInterval

This can be used to perform a function at a given interval, here, 1000 is equal to 1 second.

```javascript
setInterval(setDate, 1000);
```

- `setData` - The method to run
- `1000` - The interval to wait until running the method (again)

## style

You can use dot notation to add styles to an element extracted from the DOM.

```javascript
const secondHand = document.querySelector(".second-hand");

secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
```

Here, the transform attribute (on the HTML element with the class `second-hand`) has been given a dynamic value.

## transform-origin

This CSS attribute can be used to determine where a given transform 'pivots' from.

```CSS
transform-origin: 100%;
```

- `100%` - Moves the pivot from its default position (which is the center of the element i.e `50%`) to the end of the `x-axis`

## transition-timing-function

Useful for adding a custom transition effect.

```CSS
transition-timing-function: cubic-bezier(0, 2.11, 0.58, 1);
```

You can use **chrome dev tools** to create your `cubic-bezier`. More info on this [here](https://plus.google.com/+UmarHansa/posts/KJbumJ6wkrn)

## Tasks

- [x] - Fix the transition judder at 0/60 seconds
- [x] - Play around with the css to make prettier (add glow effect)
- [ ] - Refractor

## Solutions

The transition glitch occurs at every 0th second due to the reduction of the hand degrees back to 0 which can be seen due to the transition being set at 0.05s.

To bypass this, the transition is take away only at the 0th degree for each hand.

To add a glow effect to the clock using the `box-shadow` property. See [here](https://codersblock.com/blog/creating-glow-effects-with-css/).
