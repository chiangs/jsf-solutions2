# Module 5 Solutions

<!-- TOC -->

- [Module 5 Solutions](#module-5-solutions)
    - [02 - Changing CSS Classes with JS](#02---changing-css-classes-with-js)
    - [03 - Getting CSS with JS](#03---getting-css-with-js)
    - [04 - Changing Attributes](#04---changing-attributes)
    - [05 - Finding an element's size and position](#05---finding-an-elements-size-and-position)

<!-- /TOC -->

[Back to Module 4](../Module4/solutions.md)

## 02 - Changing CSS Classes with JS

***Create a button. Do the following when the button is clicked:***

```html
<button type="button" class="button">Button</button>
```

```js
const button = document.querySelector('.button')
```

1. Change the button's color.

```js
button.style.color = 'red'
```

2. Change the button's backgroundColor.

```js
button.style.backgroundColor = 'white'
```

3. Change the button's width.

```js
button.style.width = '300px'
```

4. Change the button's height.

```js
button.style.height = '250px'
```

[Back to top](#Module-5-Solutions)

## 03 - Getting CSS with JS

***Say you have the following HTML. Get its styles with both the style property and getComputedStyle. What's the difference between the values of these properties?***

```html
<div style="color: red; background-color: white; font-size: 5em">Big red text!</div>
```

```js
const element = document.querySelector('div')
```

1. Get style by style property

```js
const color = element.style.color
const backgroundColor = element.style.backgroundColor
const fontSize = element.style.fontSize
// returns values as strings

const style = element.style
// returns object with empty values except for the 3 defined inline
```

2. Using getComputedStyle

```js
const style = getComputedStyle(element)
// returns all 278 properties with values
```

[Back to top](#Module-5-Solutions)

## 04 - Changing Attributes

***Practice adding, and removing attributes with Element.getAttribute, Element.setAttribute and Element.dataset.***

```html
<div class="element" data-hotdogs="1"></div>
```

```js
const element = document.querySelecto('.element')
```

1. Set an attribute with `Element.setAttribute`

```js
element.setAttribute('checked', true)
```

2. Get an attribute with `Element.getAttribute`

```js
element.getAttribute('checked')
```

3. Get an attribute with `Element.dataset`

```js
const numHotdogs = element.dataset.hotdogs
// 4
```

4. Set an attribute with `Element.dataset`

```js
element.dataset.hotdogs = 6
```

5. Remove attribute with `Element.removeAttribute`

```js
element.removeAttribute('checked')
```

[Back to top](#Module-5-Solutions)

## 05 - Finding an element's size and position

[Back to top](#Module-5-Solutions)

[On to Module 6](../Module6/solutions.md)