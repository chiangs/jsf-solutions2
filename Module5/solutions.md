# Module 5 Solutions

<!-- TOC -->

- [Module 5 Solutions](#module-5-solutions)
    - [02 - Changing CSS Classes with JS](#02---changing-css-classes-with-js)
    - [03 - Getting CSS with JS](#03---getting-css-with-js)
    - [04 - Changing Attributes](#04---changing-attributes)
    - [05 - Finding an element's size and position](#05---finding-an-elements-size-and-position)
    - [06 - DOM Traversals](#06---dom-traversals)
    - [07 - Building Tabbed Component](#07---building-tabbed-component)
    - [08 - Building Carousel Component](#08---building-carousel-component)
    - [09 - Building Carousel component pt2](#09---building-carousel-component-pt2)

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

***Go to any web page, open up your console and get use getBoundingClientRect to get at the DomRect of at least one element. You should see eight values.***

## 06 - DOM Traversals

***Practice traversing the DOM with the methods taught in this lesson. With the HTML given below, do these tasks:***

```html
<div class="characters">
  <ul class="hobbits">
    <li>Frodo Baggins</li>
    <li>Samwise "Sam" Gamgee</li>
    <li>Meriadoc "Merry" Brandybuck</li>
    <li>Peregrin "Pippin" Took</li>
    <li>Bilbo Baggins</li>
  </ul>
  <ul class="humans">
    <li>Gandalf</li>
    <li>Saruman</li>
    <li>Aragorn</li>
    <li>Boromir</li>
    <li>Faramir</li>
  </ul>
  <ul class="elves">
    <li>Legolas</li>
    <li>Glorfindel</li>
    <li>Elrond</li>
    <li>Arwen Evenstar</li>
  </ul>
  <ul class="enemies">
    <li>Sauron</li>
    <li>Nazgûl</li>
  </ul>
</div>
```

1. Select `.characters` with `document.querySelector`
   
```js
const charactersList = document.querySelector('.characters')
```

2. Select `.humans` from `.characters`

```js
const humansList = charactersList.querySelector('.humans')
```

3. Select all humans with `querySelectorAll`, starting from `.humans`

```js
const humans = humansList.querySelectorAll('li')
```

4. Select all hobbits with `children`

```js
const hobbitsList = charactersList.querySelector('.hobbits')
const hobbitses = hobbitsList.children
```

5. Select the Merry (the hobbit)

```js
const merry = hobbitses[2]
```

6. Select `.enemies` from Sauron

```js
const individuals = charactersList.querySelectorAll('li')
const sauron = individuals[14]
const enemiesList = sauron.parentElement
```

7. Select the `.characters` div from Nazgûl

```js
const individuals = charactersList.querySelectorAll('li')
const nazgul = individuals[15]
const enemiesList = nazgul.parentElement
const charactersList = enemiesList.parentElement
```

8. Select Elrond from Glorfindel

```js
const charactersList = document.querySelector('.characters')
const elvesList = charactersList.querySelector('.elves')
const elves = elvesList.querySelectorAll('li')
const glorfindel = elves[1]
const elrond = glorfindel.nextElementSibling
```

9.  Select Legolas from Glorfindel

```js
const legolas = glorfindel.previousElementSibling
```

10. Select Arwen from Glorfindel

```js
const list = glorfindel.parentElement
const arwen = list[list.length -1]
```

## 07 - Building Tabbed Component

## 08 - Building Carousel Component

## 09 - Building Carousel component pt2

[Back to top](#Module-5-Solutions)

[On to Module 6](../Module6/solutions.md)