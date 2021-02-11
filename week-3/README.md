# CSS
This week, we will cover ways in which you can make new states and styles for elements on a page.


### :hover

The `:hover` property allows you to adjust the styling of elements when hovered over with a mouse.
You can target what element 

```CSS
div:hover{
	opacity: 0; //this will make the element have 0 opacity when hovered over, making it disapper;
}

```

You can target different elements on the hover by using the nested structure of html, and using a space (` `) between your css selectors to indicate a “child” element.


```HTML
<!-- We have “bar” divs nested in “rect” divs contained within a “shape” div -->
<div class="shape">
    <div class="rect">
        <div class="bar"></div>
    </div>
    <div class="rect">
        <div class="bar"></div>
    </div>
    <div class="rect">
        <div class="bar"></div>
    </div>
</div>

```

```CSS
.rect {
	width: 40px;
	height: 437px;
	background: black;
	display: inline-block;
	margin: 0px 5px;
}

.bar{
	width: 10px;
	height: 100%;
	background: red;
}

/*when you hover over any part of the shape div, all bars contained within become blue */
.shape:hover .bar{
	background: blue;
}

/*when you hover over a specific rectangle, the bar(s) contained within it will turn green */
.rect:hover .bar{
	background: green;
}

/*when you hover over any individual bar, it will turn yellow */
.bar:hover{
	background: yellow;
}
```




## CSS Transforms 
CSS transform allows you to change the shape and position of HTML elements without disrupting the normal flow. 
For 2dimensional transforms, the x-value is declared first, then the y-value.

### Transform Origin

`transform-origin` specifies the origin point of the transformation performed. This can be specified in multiple forms, including keywords, `%` values, and `px`. It is at the center of the element by default.

```CSS
.example {
  transform: rotate(-10deg);
  transform-origin: bottom left;
}
```

### Rotate
`rotate()` Rotates the div clockwise or counter-clockwise(-), specified in degrees (deg).

```CSS
.rotate {
  transform: rotate(30deg);
}
```

### 2D Translate
`translate()` moves an element sideways, up, or down. This can be specified in any length unit.

```CSS
.translate{
  transform: translate(40px, 20px);
}
```

### Scale
`scale()` stretches an element horizontally and/or vertically. Scale values are unitless. This also applies to the font-size, padding, height, and width of an element.

```CSS
.scale-preserve-ratio {
  transform: scale(.7);
}

.scale-xy {
  transform: scale(.5, 1.5);
}
```

### Skew
`skew()` stretches an element horizontally and/or vertically. Skews are defined in degrees. Contained elements, such as text, will also be skewed.

```CSS
.skew {
  transform: skew(10deg,30deg);
}
```

### Combining transforms

Multiple transforms can be applied to the same element with a space in between. (Note: you cannot declare transforms separately; the latter will override the former.) Transforms are applied in the order they are declared.
[More on transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/) including perspectival / 3D effects.

```CSS
.combined-example {
  transform: scale(.3, 1.2) rotate(30deg) skewY(-15deg) translate(50px, 20%);
}
```

## CSS Transitions
Transform functions combine well with CSS animations and transitions. 
Transitions allow property changes in CSS values to occur smoothly over a specified duration. Transitions requires a trigger (such as `:hover`) to take effect. They are declared to the element targeted for the change. (Note that by specifying the transition on the element itself, you define the transition to occur in both directions. )

`transition: background-color 1s ease-in 2s;`


\*This is shorthand notation that combines the following properties. The first unit of time is always the duration; the second the delay.

| property | description | example | 
| --- | --- | --- | 
| transition-property| property being transitioned (or use `transition-property: all`) — see [list of properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties) | `transition-property: background-color`|
| transition-duration | duration of effect, in seconds (s) or milliseconds (ms) | `transition-duration: 1s;`|
| transition-timing-function | transition style — see [common easing effects](https://codepen.io/stephengreig/pen/bHzqm) | `transition-timing-function: ease-in; `|
| transition-delay | delay until starting effect, in seconds (s) or milliseconds (ms) | `transition-delay: 2s;`


