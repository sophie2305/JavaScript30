# CSS Variables


## Variables

Like with SASS, you can create variables for your stylesheet.

``` CSS
/* Definition */
--base: #ffc600;

/* Use */
.hl {
    color: var(--base);
}
```

The prefix `--` is necessary.

**Note** - Remember, that this can be overruled due to the cascading property of CSS.

## Dataset

Can be used to access data attribute values given to HTML elements. These data elements must be prefixed with `data-`. An example is the following...

``` html
<input id="spacing" type="range" name="spacing" min="10" max="200" value="10" data-sizing="px">
```

You can access this value with the following code...

``` javascript
const suffix = this.dataset.sizing;
```
This was used to add the suffix to the sizing.