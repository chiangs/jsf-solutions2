# Module 7 Solutions

<!-- TOC -->

- [Module 7 Solutions](#module-7-solutions)
    - [01 - CSS Transitions](#01---css-transitions)
    - [02 - CSS Animations](#02---css-animations)
    - [03 - Jank Free Animations](#03---jank-free-animations)
    - [04 - Integrating transitions with js](#04---integrating-transitions-with-js)
    - [09 - GSAP](#09---gsap)

<!-- /TOC -->

[Back to Module 6](../Module6/solutions.md)

## 01 - CSS Transitions

***Create the following transitions:***

1. Create an element

```html
<div class="box"></div>
```

```css
.box {
    height: 50px;
    width: 50px;
    border: 1px solid black;
    background-color: red;
}
```

2. Change its `opacity` from 1 to 0 over 1 second when you hover on it.

```css
.box {
	height: 50px;
	width: 50px;
	border: 1px solid black;
	background-color: red;
	transition: opacity 1s ease-in-out;
}

.box:hover {
	opacity: 0;
}
```

3. Try using `ease`, `ease-in`, `ease-out`, `ease-in-out` timing functions.

ok

4. Create your own timing function with Cubic bezier.

_this is a custom ease-in-out that slides a blue box off screen and back_
```html
<section>
    <p>Custom cubic-bezier</p>
    <button class="goButton">Click Here!</button>
    <div class="box easeInOut cubicBezier" id="box"></div>
</section>
```
```css
.box {
	border: 1px solid black;
	background-color: #0091ea;
	color: #fff;
	font-weight: bold;
	height: 50px;
	width: 50px;
	transform: translateX(0);
	transition: transform 2s;
}

.go {
	transform: translateX(500px);
}

.easeInOut {
	transition-timing-function: ease-in-out;
}

.cubicBezier {
	transition-timing-function: cubic-bezier(0.74, -0.81, 0.62, 1.61);
}
```
```js
const goButton = document.querySelector('.goButton');
goButton.addEventListener('click', () => {
    const box = document.querySelector('#box');
    box.classList.add('go');
});
```

[Back to top](#Module-7-Solutions)

## 02 - CSS Animations

1. Create a `@keyframes` declaration

```css
@keyframes attention {
  from {
    -webkit-transform: translate3d(80%, 0, 0);
    transform: translate3d(80%, 0, 0);
  }
  to {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
  }
}
```

2. Write the animation with the `animation` shorthand

```css
.moving.leftArrow {
  animation: attention 1s ease-in-out infinite alternate;
}
```

3. Experiment with `animation-iteration-count`.
4. Experiment with `animation-direction`

5. Pause and play our CSS animation with `animation-play-state`.

```css
.leftArrow {
  animation-play-state: paused;
}

.leftArrow:hover {
  animation-play-state: running;
}
```

[Back to top](#Module-7-Solutions)

## 03 - Jank Free Animations

***To reduce Jank, you want to change composite properties (not layout properties, not paint properties) if you can.***

Composite properties are:

1. Translate (from the transform property)
2. Rotate (from the transform property)
3. Scale (from the transform property)
4. Opacity

[Back to top](#Module-7-Solutions)

## 04 - Integrating transitions with js

***`transitionend` and `animationend` are events you can use to tell if your transition or animation completes. They're invaluable if you need to sync up your transition or animation with JavaScript.***

_Note: This is actually really handy. A real-world use case - animating a sliding background full screen image off-screen and bringing a new one along with it without a gap and at the end take the original image, re-set and move it back to upcoming offscreen image position._

1.  Create three elements with three different `transition-property` and `transition-duration`. Use `transitionend` to remove elements when their transition completes.

```html
<button class="button" type="button">button</button>
<div class="element element1"></div>
<div class="element element2"></div>
<div class="element element3"></div>
```

```css
.element {
	height: 50px;
	width: 50px;
}

.element1 {
	background-color: #33ae74;
	transition: background-color 0.5s ease-out;
}

.element1.transition {
	background-color: #1ce;
}

.element2 {
	opacity: 0;
	transition: opacity 1s ease-in;
}

.element2.transition {
	background-color: red;
	opacity: 1;
}

.element3 {
	background-color: purple;
	transform: scale(0, 0);
	transition: transform 2s ease-in-out;
}

.element3.transition {
	transform: scale(1, 1);
}
```

```js
const button = document.querySelector('button')
const elements = document.querySelectorAll('.element')

button.addEventListener('click', () =>
	elements.forEach(element => element.classList.toggle('transition'))
)

document.addEventListener('transitionend', e => {
	const element = e.target
	element.style.display = 'none'
})
```

2.  Create three elements with three different animations. Use `animationend` to remove elements when their transition completes.

```html
<button class="button" type="button">button</button>
<div class="element element1"></div>
<div class="element element2"></div>
<div class="element element3"></div>
```

```css
.element {
	height: 50px;
	width: 50px;
}

.element1 {
	background-color: #33ae74;
}

.element1.transition {
	animation: blink 1s ease-in-out;
}

.element2 {
	background-color: red;
}

.element2.transition {
	animation: slide 3s ease-out;
}

.element3 {
	background-color: purple;
}

.element3.transition {
	animation: grow 6s ease-in;
}

@keyframes blink {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}

@keyframes slide {
	0% {
		transform: translateX(0);
	}
	100% {
		transform: translateX(50vw);
	}
}

@keyframes grow {
	0% {
		transform: scale(1);
	}
	50% {
		transform: scale(3);
	}
	100% {
		transform: scale(5);
	}
}
```

```js
document.addEventListener("animationend", e => {
    const element = e.target
    element.style.display = 'none'
})
```
[Back to top](#Module-7-Solutions)

## 09 - GSAP

_A tween is a single movement in an animation. In GSAP, a tween has the following syntax: `TweenMax.method(element, duration, vars)`_

1. Install GSAP into your project.
2. Create a tween that moves an object from 200px from the left to the right.

```html
<div class="box"></div>
```

```css
.box {
	border: 1px solid black;
	background-color: #f50057;
	width: 100px;
	height: 100px;
}
```

```js
const box = document.querySelector('.box')
// set the method `to` on the box element, pick any integer duration 
// and the x distance
TweenMax.to(box, 3, { x: 200 })
```

3. Create a tween that moves an object 200px from the top to the bottom.

```js
TweenMax.to(box, 3, { y: 200 })
```

4. Create a tween that turns an object invisible.

```js
TweenMax.to(box, 3, {opacity: 0})
```

5. Chain five tweens with TimelineMax

```js
const box = document.querySelector('.box');
const tl = new TimelineMax({});

box.addEventListener('click', () => {
	tl.from(box, 2, {
		x: 200,
		rotation: 720,
		borderRadius: 50,
		ease: 'Power1.easeOut'
	});
	tl.to(box, 2, {
		y: 400,
		ease: 'Bounce.easeOut'
	});
	tl.to(box, 1, {
		borderRadius: 0,
		x: 350,
		ease: 'Power2.easeIn'
	});
	tl.to(box, 1, {
		rotation: 90,
		transformOrigin: 'right bottom',
		ease: 'Power2.easeIn'
	});
	tl.to(box, 3, {
		y: -300,
		borderRadius: 50,
		ease: 'Bounce.easeOut'
	});
});
```

[Back to top](#Module-7-Solutions)

[On to Module 8](../Module8/solutions.md)
