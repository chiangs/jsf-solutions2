# Module 2 Solutions

<!-- TOC -->

- [Module 2 Solutions](#module-2-solutions)
    - [06 - strings, numbers, booleans](#06---strings-numbers-booleans)
    - [07 - Declaring Variables](#07---declaring-variables)
    - [08 - Functions](#08---functions)
    - [09 - Arrow Functions](#09---arrow-functions)
    - [10 - Intro to Objects](#10---intro-to-objects)
    - [11 - If/else statements](#11---ifelse-statements)
    - [12 - The `!` (NOT) operator](#12---the--not-operator)
    - [15 - Selecting an Element](#15---selecting-an-element)
    - [16 - Changing Classes](#16---changing-classes)
    - [17 - Listening to events](#17---listening-to-events)
    - [18 - Callbacks](#18---callbacks)

<!-- /TOC -->

[On to Module 3](../Module3/solutions.md)

## 06 - strings, numbers, booleans

***Prepare yourself for the next lesson by creating numbers, strings and booleans. Try the following:***

1. Create a String and console.log it

```js
const newString = 'This is a string'
```

1. Add two strings together

```js
const string1 = 'First string'
const string2 = 'Second string'

string1 + string2
// => "First stringSecond string" since I didn't specify a space.

string1 + ' ' + string2
// => "First string Second string"
```

2. Create a Number and console.log it

```js
const number = 2
console.log(number)
```

3. Add two numbers together

```js
const addTwoNumbers = 2 + 2

// or
const num1 = 1
const num2 = 2
console.log(num1 + num2)
// => 3

// or
const sum = num1 + num2
console.log(sum)
// => 3
```

1. Subtract one number from another number

```js
const num1 = 1
const num2 = 2
const difference = num1 - num2
console.log(difference)
// => -1
```

1. Multiply two numbers

```js
const num1 = 7
const num2 = 52
const product = num1 * num2
console.log(product)
// => 364
```

2. Divide one number by another number

```js
const num1 = 49
const num2 = 7
const quotient = num1 / num2
console.log(quotient)
// => 7
```

3. Create a Boolean and console.log it

[Back to top](#Module-2-Solutions)

## 07 - Declaring Variables

_Key point: If you declare a variable with `const`, you cannot reassign it with a new value. Use const whenever you can, then `let`, and refrain from using `var` now._

***Try declaring variables with both const and let. Practice assigning variables to each of them.***

The 6 primitves of JS:
- Boolean
- Null
- Undefined
- Number
- String
- Symbol (new in ECMAScript 2015) - going to skip it for now.

```js
// using const
const myBoolean = true
const myNull = null
const myUndefined = undefined
const myNumber = 3
const myDanishString = 'Hej alle sammen. Der er ingen køer på isen!'
const Symbol

// using let
let myBoolean = true
let myNull = null
let myUndefined = undefined
let myNumber = 3
let myDanishString = 'Hej alle sammen. Der er ingen køer på isen!'
let Symbol
```

[Back to top](#Module-2-Solutions)

## 08 - Functions

***Practice making functions. You need to use them a lot when you code for real. Do the following:***

1. Make a function named logger that console.log the argument you passed into it.

```js
/* declare and define the function which takes a parameter called 'parameter'
and then passes the paramter to the console.log function to print out
*/
function logger(parameter) {
    console.log(parameter)
}
/* to run this function you need to call the name of the function with '()' to execute.
Don't forget to include an argument. In this case it can take any of the primitives.
*/
logger('myArgument')
// => myArgument

logger(2)
// => 2

```
2. Make a function called add that adds two numbers together.

```js
function add(num1, num2) {
    return num1 + num2
    // or
    const sum = num1 + num2
    return sum
}
```

3. Make a function called multiply that multiplies two numbers together.

```js
function multiply(num1, num2) {
    const product = num1 * num2
    return product
}
```

[Back to top](#Module-2-Solutions)

## 09 - Arrow Functions

(Yay! I love arrow functions!)

***For this lesson, do the following:***

1. Make a function named ten that takes in zero arguments and return the value 10.Try using both () and _ syntax.

```js
const ten = () => return 10

const ten = _ => return 10

// to run remember the '()'
ten
// => the definition of the function 'ten'

ten()
// => 10
```

2. Make a function named logger that takes in one argument. It logs the argument youpassed into it. Try it with and without parenthesis ().

```js
const logger = (parameter) => console.log(parameter)

const logger = parameter => console.log(parameter)

// to run
logger('myArgument')
// => 'myArgument'
```

3. Make a function called add that adds two numbers together. Try it with and without implicit returns.

```js
const add = (num1, num2) => num1 + num2

const add = (num1, num2) => {
    return num1 + num2
}

// to run
add(2, 7)
// => 9
```

4. Make a function called multiply that multiplies two numbers together. Try it with and without implicit returns.

```js
const multiply = (num1, num2) => num1 * num2

const multiply = (num1, num2) => {
    return num1 * num2
}

// to run
multiply(52, 7)
// => 364
```

[Back to top](#Module-2-Solutions)

## 10 - Intro to Objects

***Practice making objects. You need to use them a lot when you code for real. Do the following:***

1. Make an empty object.

```js
const ferrari = {}
```
2. Make a property for your object that can be accessed with a dot notation.

```js
const ferrari = {
    color: 'red',
    engine: 'v12',
    wheels: 4,
    doors: 2,
    transmission: 'manual',
    gears: '7'
}

// Access the color property
const color = ferrari.color
```

3. Make a property for your object that can only be accessed with the bracket notation.

```js
const ferrari = {
    color: 'red',
    engine: 'v12',
    wheels: 4,
    doors: 2,
    transmission: 'manual',
    gears: '7',
    'year built': 1999
}

// Access the invalid identifier property
const yearBuilt = ferrari['year built']
```

4. Get the value of a property with the dot notation.

_(See #2)_

5. Get the value of a property with the square bracket notation. 

_(See #3)_

6. Set the value of a property with the dot notation.

```js
ferrari.color = 'blue'
console.log(ferrari)
/* =>
color: "blue"
doors: 2
engine: "v12"
gears: "7"
transmission: "manual"
wheels: 4
"year built": 1999
*/
```

7. Set the value of a property with the square bracket notation. 

```js
ferrari['year built'] = 2000
/* =>
color: "blue"
doors: 2
engine: "v12"
gears: "7"
transmission: "manual"
wheels: 4
"year built": 2000
*/
```

8.  Make a method. Call this method.

```js
const ferrari = {
    color: 'red',
    engine: 'v12',
    wheels: 4,
    doors: 2,
    transmission: 'manual',
    gears: '7',
    'year built': 1999,
    drive: function() {
        console.log('vroom vroom!')
    }
}

ferrari.drive()
// => vroom vroom!
```

9. Make a method that takes in an argument. Call this method.

```js
const ferrari = {
    color: 'red',
    engine: 'v12',
    wheels: 4,
    doors: 2,
    transmission: 'manual',
    gears: '7',
    'year built': 1999,
    drive: function() {
        console.log('vroom vroom!')
    },
    changeGear: function(gear) {
        console.log('shifting to gear ' + gear)
    }
}

ferrari.changeGear(6)
// => shifting to gear 6
```

[Back to top](#Module-2-Solutions)

## 11 - If/else statements

***Controlling the flow of a program with if/else statements is incredibly important. Try the following exercises:***

```js
const james = 22
const valerie = 25
const kenneth = 27
```

_James is 22 years old, Valerie is 25 years old, Kenneth is 27 years old. Answer the following questions with the above code:_

1. Make an if/else statement to check if you are younger than James.

```js
const me = nunya (jk)

const me = 36

// expected answer for this lesson
if (james > me) {
    console.log(true)
} else {
    console.log(false)
}

// bonus* (using ternary)
james > me ? true : false

// or

const isJamesOlder = james > me ? true : false
console.log(isJamesOlder)

// => false
```

2. Make an else if statement within your if/else to check if you are older than Valerie.

```js
if (james > me) {
    console.log(true)
} else if (me > valerie) {
    console.log(true)
} else {
    console.log(false)
}

// bonus* (using ternary)
const result = james > me ? true : me > valerie ? true : false
console.log(result)

// => true
```

3. Make another else if statement to check if you're as old as Kenneth.

When you do the above exercise, try comparing values with

    > and >=
    < and <=
    ===
    !==

```js
if (me >= kenneth) {
    console.log('maybe')
} else {
    console.log(false)
}

// or

if (me === kenneth) {
    console.log(true)
} else {
    console.log(false)
}

// or

if (me !== kenneth) {
    console.log(false)
} else if (me > kenneth) {
    console.log('older')
} else {
    console.log('younger')
}

// bonus* (using ternary)
const oldAsKenneth = me === kenneth ? true : false

// => false
```

_Answer the rest of the questions below with reference to the following code:_

```js
if (someValue) {
  // Executes if true
} else {
  // Executes if false
}
```

Would the if statement above execute:

- If someValue is false?  yes. the code block in the else condition executes.
- If someValue is true? yes. the code block in the if condition executes.
- If someValue is null? yes. null is falsey, so the else condition applies.
- If someValue is undefined? undefined is also falsey. so the else condition applies.
- If someValue is 0? yes. 0 is falsey. so the else condition applies.
- If someValue is -1? yes. -1 is truthy so the if condition block executes.
- If someValue is ''?  an empty string is falsey. so the else condition applies.
- If someValue is 'has a value!'? this is a valid string, so the if condition applies.
- If someValue is {}? an empty object is, although empty, is a complete and valid object, so the if block executes.
- If someValue is { isHavingFun: true }?  this is a defined object, so like the one above, executes the if block. 
- If someValue is []? Same as the empty object.
- If someValue is ['one', 'two', 'three']? Same as the empty array.

_Be wary of the 0 since it is falsey. I have had a few use cases where I was testing on the condition that an object had a value set to one of the properties, but in a few cases the object could have the number 0 set as the value...well guess what? That took awhile to debug because my if/else looked like this:_

```js
if (object.property) {
    // do something
} else {
    // do something
}

// This always executed the else even if the object had the property, because 0 is falsey. so refactoring looked like this:

if (object.property >= 0)
```

[Back to top](#Module-2-Solutions)

## 12 - The `!` (NOT) operator

***What values would you get for each of these expressions?***

1. !2550284 => false
2. !true => false
3. !NaN => true
4. !{} => false
5. !!'Pandas are adorable!' => false
6. !!'' => false

[Back to top](#Module-2-Solutions)

## 15 - Selecting an Element

***Practice selecting Elements with document.querySelector and Element.querySelector. Try using ids, classes, tags and attribute selectors as you select from the following HTML.***

```html
<ul id="star-wars-characters">
  <li class="character luke" data-type="hero">Luke Skywalker</li>
  <li class="character yoda" data-type="master">Yoda</li>
  <li class="character badboy" data-type="villain">Darth Vader</li>
</ul>
```

1. Get the #star-wars-characters list with id and tag selectors.

```js
// by id
const starWarsCharList = document.querySelector('#star-wars-characters')
//or
const starWarsCharList = document.getElementById('star-wars-characters')

// by tag
const starWarsCharList = document.querySelector('ul')
```

From the #star-wars-characters list, get the following:

1. Luke Skywalker with class, tag and attribute selectors

```js
const luke = starWarsCharList.querySelector('.luke')
const luke = starWarsCharList.querySelector('.li')
const luke = starWarsCharList.querySelector('[data-type="hero"]')
```

2. Yoda with class and attribute selectors

```js
const yoda = starWarsCharList.querySelector('.yoda')
const yoda = starWarsCharList.querySelector('[data-type="master"]')
```

3. Darth Vader with class and attribute selectors

```js
const vader = starWarsCharList.querySelector('.badboy')
const vader = starWarsCharList.querySelector('[data-type="villain"]')
```

4. Notice how you can't select Yoda and Darth Vader with tags when you use querySelector.

No, but you could iterate through starWarsCharList like an array or do this:

```js
const yoda = starWarsCharList[1]
```

[Back to top](#Module-2-Solutions)

## 16 - Changing Classes

Practice adding, removing, checking for classes and toggling classes with Element.classList. Work through the examples in this HTML:

```html
<div class="add">Add a "red" class to me!</div>

<div class="remove">Remove the class, "remove" from me!</div>

<div class="contains">
  <div>Do I have a "blue" class?</div>
  <div class="blue">Do I have a "blue" class?</div>
</div>

<div class="toggle">Do I have a "red" class? If yes, remove it. If no, add it.</div>
```

```js
// 1
const addElement = document.querySelector('.add')
addElement.classList.add('red')

// 2
const removeElement = document.querySelector('.remove')
removeElement.classList.remove('remove')

// 3
const containsElement = document.querySelector('.contains')
const divs = containsElement.querySelectorAll('div')
/* divs is now an array of child elements of the contains div, 
so for each of of the child elements, I want to check their classList 
and add or remove the blue class
*/
divs.forEach(element => {
    if (element.classList.contains('blue')) {
        element.classList.remove('blue')
    } else {
        element.classList.add('blue')
    }
})

// 4
const toggleElement = document.querySelector('.toggle')
toggleElement.classList.toggle('red')
```

[Back to top](#Module-2-Solutions)

## 17 - Listening to events

***Practice adding event listeners and getting them to do things. You'll use them a lot when you write components. Do the following:***

1. Write an click event listener. Log something into the console so you know the listener works.

```html
<button type="button" class="button">Button</button>
```

```js
/* basic solution
1. Select the button in the DOM
2. Attach the click listener
*/
const button = document.querySelector('.button')
button.addEventListener('click', function(e) {
    console.log('button clicked')
})

/* alternate solution
1. Define the click message
2. Selecte the button in the DOM
3. Attach the listener using arrow function
*/
const clickMsg = 'button clicked'
const button = document.querySelector('.button')

button.addEventListener('click', () => console.log(clickMsg))
```

2. Check the existence of the listener with Firefox's devtools.

3. Check the existence of the listener with Chrome Devtools.

4. Add a class to the component when it is clicked. Remove a class from the component when it is clicked again.

```js
button.addEventListener('click', () => button.classList.toggle('myClass'))
```

[Back to top](#Module-2-Solutions)

## 18 - Callbacks

***No exercise required for this lesson. There's only one thing to know: a callback is a function that is passed into another function as an argument to be executed later.***

[Back to top](#Module-2-Solutions)

[On to Module 3](../Module3/solutions.md)