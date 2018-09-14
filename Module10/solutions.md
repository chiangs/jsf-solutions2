# Module 10 Solutions

<!-- TOC -->

- [Module 10 Solutions](#module-10-solutions)
  - [01 - Changing text and HTML](#01---changing-text-and-html)
  - [02 - Creating HTML elements](#02---creating-html-elements)
  - [03 - Adding multiple elements to the DOM](#03---adding-multiple-elements-to-the-dom)
  - [04 - Removing Elements from the DOM](#04---removing-elements-from-the-dom)

<!-- /TOC -->

[Back to Module 9](../Module9/solutions.md)

## 01 - Changing text and HTML

```html
<div class="container"></div>
```

1. Change an element's text with textContent

```js
const container = document.querySelector('.container')
container.textContent = 'Have you seen my stapler?'
```

2. Change an element's inner HTML with innerHTML

```js
container.innerHTML = '<p class="textContent">Ahoy Matey!</p>'
```
## 02 - Creating HTML elements

***Practice creating and adding elements to the DOM. Say you have the following HTML***

```html
<div class="characters">
  <ul class="hobbits">
    <li>Frodo Baggins</li>
    <li>Samwise "Sam" Gamgee</li>
    <li>Meriadoc "Merry" Brandybuck</li>
    <li>Peregrin "Pippin" Took</li>
  </ul>
  <ul class="elves">
    <li>Glorfindel</li>
    <li>Elrond</li>
    <li>Arwen Evenstar</li>
  </ul>
  <ul class="humans">
    <li>Gandalf</li>
    <li>Saruman</li>
    <li>Boromir</li>
    <li>Faramir</li>
  </ul>
</div>
```

1. Create a list item, <li>Bilbo Baggins</li>, and add it as the last item in .hobbits

```js
// First create the list item, then add the text
const bilbo = document.createElement('li')
bilbo.textContent = `Bilbo Baggins`

// To insert bilbo, we need to select the hobbits div first
const hobbitsList = document.querySelector('.hobbits')

// Use appendChild to add bilbo to the end of the list
hobbitsList.appendChild(bilbo)

```

2. Create a list item, <li>Legolas</li>, and insert it as the first item in .elves.

```js
const legolas = document.createElement('li')
legolas.textContent = `Legolas`

const elvesList = document.querySelector('.elves')
const glorfindel = elvesList[0]

elvesList.insertBefore(legolas, glorfindel)
```

3. Create a list item, <li>Aragorn</li>, and insert it before <li>Boromir</li>.

```js
const aragorn = document.createElement('li')
aragorn.textContent = `Aragorn`

const humansList = document.querySelector('.humans')
const boromir = humansList[2]
humansList.insertBefore(aragorn, boromir)
```

[Back to top](#Module-10-solutions)

## 03 - Adding multiple elements to the DOM

```html
<div class="characters">
  <ul class="elves">
    <li>Legolas</li>
    <li>Arwen Evenstar</li>
  </ul>
</div>
```

1. Add a list of humans to .characters. This list should have a humans class and contains five list items—Gandalf, Saruman, Aragon, Boromir, and Faramir.

```js
// Declare the list of characters as an array of strings
const characters = [
  'Gandalf,' 
  'Saruman,' 
  'Aragon,' 
  'Boromir,' 
  'Faramir'
]
// Map the array into list items and joining them
const htmlString = characters.map(character => `<li>${character}</li>`).join(' ')

// Create the list and append it to the characters div
const humans = document.createElement('ol')
humans.classList.add('humans')

// select the outer list to add list
const charactersList = document.querySelector('.characters')
charactersList.innerHTML += charactersList.innerHTML + charactersList

// finally add the new list items to the characters unordered list element
charactersList.innerHTML = htmlString
```
   
2. Add two list items—Glorifendel and Elrond—before Arwen Evenstart. Use the document fragment method.

```js
// Create the fragment
const fragment = document.createDocumentFragment()

// Crreate the array of characters to add
const newCharacters = [
  'Glorifendel',
  'Elrond'
]

// Turn them into string templates
newCharacters.forEach(character => {
  const li = document.createElement('li')
  li.innerHTML = dev
  fragment.appendChild(li)
})

// Select Arwen to append the items before
const elves = document.querySelector('.elves')
const arwen = humansList[1]
elves.insertBefore(fragment, arwen)
```

[Back to top](#Module-10-solutions)

## 04 - Removing Elements from the DOM

```html
<ol class="humans">
  <li>Gandalf</li>
  <li>Saruman</li>
  <li>Aragorn</li>
  <li>Boromir</li>
  <li>Faramir</li>
</ol>
```

1. Remove Aragon from the following HTML.

```js
const aragon = document.querySelectorAll('li')[2]
aragon.parentNode.removeChild(aragon)
```

2. Add it to the end of the list.

```js
aragon.parentNode.appendChild(aragon)
```

[Back to top](#Module-10-solutions)

[On to Module 11](../Module11/solutions.md)