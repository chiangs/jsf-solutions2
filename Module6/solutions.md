# Module 6 Solutions

<!-- TOC -->

- [Module 6 Solutions](#module-6-solutions)
    - [01 - The listening element](#01---the-listening-element)
    - [02 - Default Behaviors](#02---default-behaviors)
    - [03 - Event Propogation](#03---event-propogation)
    - [04 - Event Delegation](#04---event-delegation)
    - [05 - Removing event listeners](#05---removing-event-listeners)
    - [06 - Improving Modal](#06---improving-modal)
    - [07 - Improving Accordion](#07---improving-accordion)

<!-- /TOC -->

[Back to Module 5](../Module5/solutions.md)

## 01 - The listening element

***`this` only works if you use normal functions (not arrow functions) while `currentTarget` works regardless of what type of functions you use.***

I default to writing arrow functions nowadays, so I almost always go for `currentTarget`.

1. Get the listening element with `this`.

```js
const element = document.querySelector('element')
element.addEventListener('click', function(e) {
  console.log(this)
})
```

2. Get the listening element with `Event.currentTarget`.

```js
element.addEventListener('click', e => console.log(e.currentTarget))
```

[Back to top](#Module-6-Solutions)

## 02 - Default Behaviors

1. A link with a `href` that points to `google.com`

```html
<a class="link" href="https://www.google.com" target="_blank" rel="noopener noreferrer">Google</a>
```

```js
const link = document.querySelector('.link')
link.addEventListener('click', e => e.preventDefault())
```

2. A checkbox

```html
<form>
 <input type="checkbox" name="perkele" value="perkele" id="perkele">
 <label for="perkele">Perkele!</label>
</form>
```

```js
const checkbox = document.querySelector('input')
checkbox.addEventListener('click', e => e.preventDefault())
// verify that the checkbox does NOT get checked when clicked due to preventDefault()
```

[Back to top](#Module-6-Solutions)

## 03 - Event Propogation

Three phases occur when an event is fired:

1. The capturing phase
2. The target phase
3. The bubbling phase

Together, they're called **event propagation**.

If you want to prevent an event from bubbling, you can use `stopPropagation` or `stopImmediatePropagation`.

- `stopPropagation` prevents events from bubbling upwards
- `stopImmediatePropagation`  prevents events from bubbling upwards, and also prevents subsequent events on the listening element from firing.

***Exercise**

```html
<div class="box box1">
  <span>Box 1</span>
  <div class="box box2">
    <span>Box 2</span>
    <div class="box box3"> <span>Box 3</span> </div>
  </div>
</div>
```

```js
const boxes = document.querySelectorAll('.box')
```

1. Add an event listener in the capturing phase

```js
boxes.forEach(box => 
    box.addEventListener('click', e => 
        console.log(e.eventPhase, e.currentTarget), true)
)
```

2. Add an event listener in the bubbling phase

```js
boxes.forEach(box => 
    box.addEventListener('click', e => 
        console.log(e.eventPhase, e.currentTarget), false)
)
```

Answer these questions:

1. Which phase comes first? The capturing phase or the bubbling phase? - ***capturing***
2. What event listeners are fired in the capturing phase? - ***the ones that have useCapture = true***
3. What event listeners are fired in the target phase? - ***all attached to the target***
4. What event listeners are fired in the bubbling phase? - ***listeners WITHOUT useCapture***
5. How do you stop an event from bubbling? - ***stopPropagation or stopImmediatePropagation***

[Back to top](#Module-6-Solutions)

## 04 - Event Delegation

```html
<ul>
  <li><a href="#">Benjamin Franklin</a></li>
  <li><a href="#">Thomas Edison</a></li>
  <li><a href="#">Franklin Roosevelt</a></li>
  <li><a href="#">Napolean Bonaparte</a></li>
  <li><a href="#">Abraham Lincoln</a></li>
</ul>
```

***Here's a list of famous people. Do the following:***

1. Create an event listener that uses the event delegation pattern.

```js
const list = document.querySelector('ul')
list.addEventListener('click', e => console.log(e))
```

2. Log the element if the target matches `li`

```js
list.addEventListener('click', e => {
    if (e.target.matches('a')) {
        console.log(e)
    }
})
// Should only fire when the name is clicked
```

3. Try using both `pointer events` and `closest` to filter the event target

```css
li * {
    pointer-events: none;
}
/* targets the li */
```

```js
list.addEventListener('click', e => {
    if (e.target.closest('li')) {
        console.log(e)
    }
})
// targets the li
```

[Back to top](#Module-6-Solutions)

## 05 - Removing event listeners

***Do the following:***

```html
<button type="button">button</button>
```

```js
const buttonCallback = e => console.log(e)
const button = document.querySelector('button')
```

1. Add a `click` event listener.

```js
button.addEventListener('click', e => buttonCallback(e))
```

2. Remove the event listener you've added.

```js
button.removeEventListener('click', e => buttonCallback(e))
```

3. Create an event listener that listens for five clicks.

```js
// define the counter to track clicks
// define a callback function that adds the clicks and prints the current click count
let counter = 0
const addClick = _ => {
    counter += 1
    console.log('clicked: ' + counter + ' times')
}

// actual callback function to be used by the event listener that also uses the other functions
const clickCallback = e => 
    counter === 5 ? button.removeEventListener('click', clickCallback ) : addClick()

// non ternary version
const clickCallback = e => {
    addClick()
    if (counter === 5) {
        button.removeEventListener('click', clickCallback)
    }
}

// Attach the listener
button.addEventListener('click', clickCallback)
```

[Back to top](#Module-6-Solutions)

## 06 - Improving Modal

Feel free to PR your version up to this. I will add mine on the completed modal.

## 07 - Improving Accordion

Same same as above

[On to Module 7](../Module7/solutions.md)