# Module 2 Solutions

<!-- TOC -->

- [Module 2 Solutions](#module-2-solutions)
    - [2.6 - strings, numbers, booleans](#26---strings-numbers-booleans)
    - [2.7 Declaring Variables](#27-declaring-variables)
    - [2.8 Functions](#28-functions)
    - [2.9 Arrow Functions](#29-arrow-functions)

<!-- /TOC -->

## 2.6 - strings, numbers, booleans

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

## 2.7 Declaring Variables

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

## 2.8 Functions

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

## 2.9 Arrow Functions

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
