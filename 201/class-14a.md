# CSS Animations, Transforms, Transitions

### Transitions and Animations

Transitions can be done with CSS using four different related properties *transition-property, transition-duration, transition-timing-function, transition-delay*. Transitions can be applied to pseudo-classes to help trigger the effects, *:hover, :focus, :active,* and *:target*.

```css
.potato {
    background: #2db34a;
    border-radius: 6px
    transition-property: background, border-radius;
    transition-duration: 1s;
    transition-timing-function: linear;
  }
  .potato:hover {
    background: #ff7b29;
    border-radius: 50%;
  }
```

Transitions can also be done with shorthand such as the following.

```css
.potato {
  background: #2db34a;
  border-radius: 6px;
  transition: background .2s linear, border-radius 1s ease-in 1s;
}
.potato:hover {
  color: #ff7b29;
  border-radius: 50%;
}
```

### Animations

Animations are accomplished by ***@keyframes*** and animation properties.

```css
.stage:hover .potato {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```

```css
@keyframes potato{
  0% {
    left: 0;
    top: 0;
  }
  100% {
    left: 88px;
    top: 0;
  }
}
```

### Transform

Transform helps you manipulate with CSS in simpler ways such as making things grow, shrink, or rotate 180 degrees. Transform has properties such as *scale, translate, rotate, *and *skew*. Transforms can be longhand or shorthand.

```css
transform: scale(1.2);
transform: translateY(80px);
transform: translateX(100px);
```

```css
transform: scale(1.2) translate(100px, 80px);
```
