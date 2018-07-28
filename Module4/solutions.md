# Module 4 Solutions

<!-- TOC -->

- [Module 4 Solutions](#module-4-solutions)
    - [01 - Arrays](#01---arrays)
    - [02 - For loops](#02---for-loops)
    - [03 - ForEach loop](#03---foreach-loop)
    - [04 - Selecting multiple elements](#04---selecting-multiple-elements)
    - [05 - Nodes vs. Elements](#05---nodes-vs-elements)
    - [06 - Building an accordion](#06---building-an-accordion)

<!-- /TOC -->

[Back to Module 3](../Module3/solutions.md)

[On to Module 5](../Module5/solutions.md)

## 01 - Arrays

***Arrays are important in JavaScript. Practice them well. Here are some exercises and questions for you to try out.***

1.  Make an empty array that contains nothing.

```js
const newArray = []
```

2.  Make an array that contains three items.

```js
const anotherArray = [24, 'a string', false]
```

***The following questions require you to make use of the people array provided below.***

```js
const people = [
  'Benjamin Franklin',
  'Thomas Edison',
  'Franklin Roosevelt',
  'Napolean Bonaparte',
  'Abraham Lincoln',
  'Mother Theresa',
  'Mahatma Gandhi',
  'Winston Churchill',
  'Charles Darwin',
  'Albert Einstein',
  'Pablo Picasso',
  'Ludwig Beethoven',
  'Walt Disney',
  'Henry Ford',
  'Steve Jobs'
]
```

1. What is the index of Mahatma Gandhi in this list of people?

```js
console.log(people[6])
// => Mahatma Gandhi
```

2. Get Pablo Picasso from the people array.

```js
const picasso = people[10]
console.log(picasso)
// => Pablo Picasso
```

3. Set Walt Disney to Disneyland.

```js
people[12] = 'Disney'
```

4. Add your best friend's name to the end of the list.

```js
people.concat('VS Code')
```

5. Add another friend's name to the start of the list.

```js
const friend = ['Macbook Pro']
const combinedArray = friend.concat(people)
```

6. Add your name after Winston Churchill in the list.

```js
// Winston Churchill = people[7], so we need to slice up to index 8 to include him in the first part
const firstPart = people.slice(0, 8)
const lastPart = people.slice(8)
const toAdd = ['Stephen']
const combinedArray = [].concat(firstPart, toAdd, lastPart)
```

6. Remove Benjamin Franklin from this list.

```js
// BennyJ is people[0]
const noBennies = people.slice(1)
```

7. Remove Steve Jobs from this list.

```js
// Stevie is last
const noSteves = people.slice(0, persons.length-1)
```

7. Remove Napolean Bonaparte from this list

```js
// Shawty is people[3]
const firstPart = people.slice(0, 3)
const secondPart = people.slice(4, people.length)
const noNapoleon = [].concat(firstPart, secondPart)
```

[Back to Top](#Module-4-Solutions)

## 02 - For loops

```js
const numbers = [1, 12, 4, 18, 9, 7, 11, 3, 50, 5, 6]
```

1. Loop through the numbers and console.log each number within.

```js
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i])
}

// or

numbers.forEach(number => console.log(number))
```

2. Loop through the numbers. If the numbers are greater than 5, console.log them.

```js
for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 5) {
        console.log(numbers[i])
    }
}

// or

numbers.forEach(number => {
    if (number > 5) {
        console.log(number)
    }
})
```

3. Create a new array. Add all numbers that are greater than 10 into this new array. (Hint: You have to loop through the numbers array first).

```js
let over10 = []
for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 10) {
        over10 = over10.concat(numbers[i])
    }
}

// or
let over10 = []
numbers.forEach(number => {
    if (number > 10) {
        over10 = over10.concat(number)
    }
})
```

4. Create a new array. Multiply all numbers by 5 and put them into the new array. (Hint: You have to loop through the numbers array first).

```js
let newArray = []
for (let i = 0; i < numbers.length; i++) {
    newArray = newArray.concat(numbers[i] * 5)
}

// or
numbers.forEach(number => newArray = newArray.concat(number * 5))
```

[Back to Top](#Module-4-Solutions)

## 03 - ForEach loop

***Practice using forEach through an array of people (given below). Do the following:***

```js
const people = [
  { firstName: 'Benjamin', lastName: 'Franklin', yearOfDeath: 1790 },
  { firstName: 'Thomas', lastName: 'Edison', yearOfDeath: 1931 },
  { firstName: 'Franklin', lastName: 'Roosevelt', yearOfDeath: 1945 },
  { firstName: 'Napolean', lastName: 'Bonaparte', yearOfDeath: 1821 },
  { firstName: 'Abraham', lastName: 'Lincoln', yearOfDeath: 1865 },
  { firstName: 'Mother', lastName: 'Theresa', yearOfDeath: 1962 },
  { firstName: 'Mahatma', lastName: 'Gandhi', yearOfDeath: 1948 },
  { firstName: 'Winston', lastName: 'Churchill', yearOfDeath: 1965 },
  { firstName: 'Charles', lastName: 'Darwin', yearOfDeath: 1882 },
  { firstName: 'Albert', lastName: 'Einstein', yearOfDeath: 1955 },
  { firstName: 'Pablo', lastName: 'Picasso', yearOfDeath: 1973 },
  { firstName: 'Ludwig', lastName: 'Beethoven', yearOfDeath: 1827 },
  { firstName: 'Walt', lastName: 'Disney', yearOfDeath: 1966 },
  { firstName: 'Henry', lastName: 'Ford', yearOfDeath: 1947 },
  { firstName: 'Steve', lastName: 'Jobs', yearOfDeath: 2012 }
]
```

1. console.log the first name of each person in the array.

```js
people.forEach(person => console.log(person.firstName))
```

2. Make a second array that contains only the first name of each person.

```js
let newArray = []
people.forEach(person => newArray = newArray.concat(person.firstName))
```

3. Make a third array that contains people that have died after 1950.

```js
let after1950 = []
people.forEach(person => {
    if (person.yearOfDeath > 1950) {
        after1950 = after1950.concat(person)
    }
})
```

4. Find index of Charles Darwin in the array.

```js
let charlesIndex = 0
people.forEach((person, index) => {
    if (person.firstName === 'Charles') {
        charlesIndex = index
    }
})

// or use findIndex
people.findIndex(person => person.lastName === 'darwin')

// to be more specific and reduce errors match on first and last name and convert everything to lowercase
people.findIndex(person => person.firstName.toLowerCase() === 'charles' && person.lastName.toLowerCase() === 'darwin')

// => 8
```

[Back to Top](#Module-4-Solutions)

## 04 - Selecting multiple elements

***Practice selecting Elements with querySelectorAll.***

```html
<div id="star-wars">
  <div class="character" data-type="good-guy">Luke Skywalker</div>
  <div class="character" data-type="good-guy">Yoda</div>
  <div class="character" data-type="villain">Darth Vader</div>
</div>
```

1. Select all good guys with attributes.

```js
const goodGuys = document.querySelectorAll('[data-type="good-guy"]')
```

2. Give good guys a `yay` class

```js
goodGuys.forEach(guy => guy.classList.add('yay'))
```

3. Select all villains with attributes.

```js
const villains = document.querySelectorAll('[data-type="villain"]')
```

4. Give villains a nay class.

```js
villains.forEach(villain => villain.classList.add('nay'))
```

5. Select all characters through the character class.

```js
const characters = document.querySelectorAll('.character')
```

6. Give all characters a star-wars class.

```js
characters.forEach(character => character.classList.add('star-wars'))
```

[Back to Top](#Module-4-Solutions)

## 05 - Nodes vs. Elements

***An Element is a specific type of Node. Since an Element is a Node, they have all the properties and methods that Nodes have.***

[Back to Top](#Module-4-Solutions)

## 06 - Building an accordion

As with the modal, I've already completed the animated one so that will be included later. Please feel free to PR your version of the basic accordion for this lesson.

[Back to Top](#Module-4-Solutions)

([On to Module 5](../Module5/solutions.md))