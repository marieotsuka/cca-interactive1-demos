# CSS Animations

Using just CSS, you can create animation sequences for any element. (Animations allow motion without triggers.)
Animations consist of *two separate sets* of CSS declarations:
- **@keyframes**: specifies the state of the element at a certain time point (relative to defined timing of animation.)
- **animation properties** apply the keyframe animation to one or many elements

```CSS
@keyframes changecolor {
  0% {
    background-color: blue;
  }
  50% {
    background-color: yellow;
    color: rgba(200,155,20,0.8);
  }
  100% {
    background-color: green;
  }
}

#animated-div{
  animation: changecolor 3.5s linear 0.2s 3 alternate;
}
```
<div class="button" id="animation-demo">
  Run
</div>

<div id="animated div" style="padding: 1em; margin: 1em; animation: changecolor 3.5s linear 0.2s 3 alternate;">
  Animation Demo
</div>


- `changecolor` is the identifier — your name for the animation. This must match the name used to declare animation properties
- The nested brackets, or keyframes are the timestamps / waypoints in the animation. You can use `from`,`to`, `%` to specify these points.


\*This animation shorthand notation that combines the following properties. The first unit of time is always the duration; the second the delay.

| property | description | example | 
|---|---|---|
| animation-name | identifier given to animation in @keyframes declarations, any name without spaces | `animation-name: changecolor;`|
| animation-duration | duration of animation, which is broken up into the waypoints defined in keyframes, in seconds (s) or milliseconds (ms) | `animation-duration: 3.5s;`|
| animation-timing-function | animation style, same as transitions | `animation-timing-function: linear; `|
| animation-delay | delay until starting animation, in seconds (s) or milliseconds (ms) | `animation-delay: 0.2s;`|
| animation-iteration-count | number of times the animation runs, `infinite` or numbers | `animation-iteration-count: 3;`|
| animation-direction | from what direction the animation begins, `normal`, `reverse`, `alternate`, `alternate-reverse` | `animation-direction: alternate;`|
| animation-play-state |whether to play or pause, `running` (default), `paused` | `animation-play-state: running;`|
| animation-fill-mode | whether to apply styles before and after the animation executes, `none` (default), `forwards`, `backwards`, `both` | `animation-fill-mode: none;`|

### Animations and transforms
Transitions and animations can also be combined with any “animatable” CSS property, but we should be careful as some properties may eat up some of your performance (and your animation may appear choppy.) Not all properties are “animatable.” Transform properties lend well to transitions and animations. Variable font properties can also be animated.


