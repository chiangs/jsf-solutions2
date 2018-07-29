# Module 8 Solutions

<!-- TOC -->

- [Module 8 Solutions](#module-8-solutions)
    - [01 - Ternary operators (yay!)](#01---ternary-operators-yay)
    - [02 - And - Or operators](#02---and---or-operators)
    - [03 - Early returns](#03---early-returns)
    - [04 - Template literals](#04---template-literals)
    - [05 - Destructure](#05---destructure)
    - [06 - Default value](#06---default-value)
    - [07 - Enhanced Object Literals](#07---enhanced-object-literals)
    - [08 - Rest and spread](#08---rest-and-spread)
    - [09 - Useful array methods](#09---useful-array-methods)
    - [11 - Looping through objects](#11---looping-through-objects)
    - [12 - Implicit return object](#12---implicit-return-object)

<!-- /TOC -->

[Back to Module 7](../Module7/solutions.md)

## 01 - Ternary operators (yay!)

***Which function executes in the code below? `walk()` or `stop()`?***

```js
const lightColor = 'red'

lightColor === green
  ? walk()
  : stop()
```

**ANSWER: `stop()`**
_green is never defined or is a typo and is supposed to be 'green', if const green = 'red' then `walk()` would execute._

***Find the index of `apple` in the `fruitBasket`. Then, use a ternary operator to decide between two functions, `eat()` or `wash()`. If the `index` of the apple is 2, run `eat()`. Otherwise, run `wash()`.***

```js
const fruitBasket = ['apple', 'pear', 'orange']
let appleIndex
const wash = _ => console.log('wash that fruit')
fruitBasket.forEach((fruit, index) => {
    if (fruit === 'apple') {
        appleIndex = index
        console.log(appleIndex)
    }
})
appleIndex === 2 ? eat() : wash()
```

***What is `finalNum` in the following code?***

```js
const num = 5
const square = num => num * num
const add = num => num + num

const finalNum = num > 5 ? square(num) : add(num)
```

**ANSWER: 10***

[Back to top](#Module-8-Solutions)

## 02 - And - Or operators

What value would you get for each of the following expressions?

1. `'Benjamin' && 'Thaddeus'`   => 'Thaddeus'
2. `'Benjamin' || 'Thaddeus'`   => 'Benjamin'
3. `'' && null`                 => ''
4. `'' || null`                 => null
5. `2550284 && 0`               => 0
6. `2550284 || 0`               => 2550284

[Back to top](#Module-8-Solutions)

## 03 - Early returns

***You want to use early returns for two situations:***

1. To reduce nested code
2. To remove the need for `else if` statements

## 04 - Template literals

1. `console.log` a string that contains a variable with template literals

```js
const sayName = (firstName, lastName) => {
  console.log(`${firstName} ${lastName}`)
}

sayName('Stephen', 'Chiang') // Zell Liew
```

2. `console.log` a string that spans multiple lines with template literals

```js
const viewContent = `Lorem ipsum dolor sit amet, consectetur adipisicing elit. 
Ipsa illo dolore explicabo deserunt a officiis quidem labore. 
Laborum assumenda hic soluta reprehenderit explicabo exercitationem, nulla aspernatur. 
Expedita laborum eveniet blanditiis.`
```

[Back to top](#Module-8-Solutions)

## 05 - Destructure

***Perform these actions with the following set of data:***

```js
const posts = [{
  id: 800,
  title: 'This is 💩'
}, {
  id: 801,
  title: 'Pooing is a natural thing.'
}, {
  id: 802,
  title: 'Poo jokes are getting irritating'
}]
```

1. Get the first two items in `posts` with destructuring.

```js
const [firstItem, secondItem] = posts
```

2. Get the `id` and `title` of the first post with destructuring.

```js
const {id, title} = firstItem
```

3. Rename the `title` of the first post to `content` while you destructure.

```js
const {id, title:content} = firstItem
```

4. Create a `description` variable and provide it with a default value `Nothing is better than leaving the description empty`.

```js
const { description = 'Nothing is better than leaving the description empty' } = firstItem
```

[Back to top](#Module-8-Solutions)

## 06 - Default value

1. Create a function, `signUpForPlan`, that takes in one parameter, `plan`. `plan` defaults to `basic`.

```js
const signUpForPlan = (plan = 'basic') => console.log(plan)
```

2. Create a function, `createEmployee` that takes in an object
  1. The object has five properties:
    1. First Name
    2. Last Name
    3. Age
    4. Gender
    5. Position
  2. Position can be default to `associate`.

```js
const createEmployee = (employee) => {
    const { 
        position = 'associate'
    } = employee
    employee.position = position
    return employee
}

createEmployee({
firstName: 'stephen', lastName: 'chiang', age: 36, gender: 'm'})
// => gets default position: 'associate' in object

createEmployee({
firstName: 'stephen', lastName: 'chiang', age: 36, gender: 'm', position: 'ceo'})
// => gets 'ceo' in object
```

[Back to top](#Module-8-Solutions)

## 07 - Enhanced Object Literals

1. Try creating a property with property value shorthands

```js
const make = 'ferrari'

const ferrari = { make }

// => Object { make: "ferrari" }
```

2. Try creating a method with method shorthands

```js
const ferrari = {
    drive() {
        console.log('vroom vroom!')
    }
}

ferrari.drive()
// => 'vroom vroom!'
```

3. Try adding two dynamic variables into Javascript with computed property names

```js
const property = 'model'
const property2 = 'make'
const ferrari = {
  [property]: 'Italia',
  [property2]: 2018,
  [property2 + property]: 'Italia 2018'
}

console.log(ferrari.makemodel)
// => Italia 2018
```

[Back to top](#Module-8-Solutions)

## 08 - Rest and spread

***Practice using spread and rest operators by doing the following:***

1. Spread an array

```js
const array = [1,2,3,4,5]
console.log(...array)
```

2. Spread an array when calling a function

```js
const logNumbers = (first, second, third) => {
    console.log(first)
    console.log(second)
    console.log(third)
}

logNumbers(...array)
```

3. Concatenate arrays with spread

```js
const array1 = [1, 2, 3, 4, 5]
const array2 = ['a', 'b', 'c', 'd', 'e']
const combinedArray = [...array1, ...array2]
```

4. Use the rest operator as a function argument

```js
const logNumbers = (...numbers) => numbers.forEach(number =>  console.log(number))
logNumbers(1,10,99,25,32,2)
```

5. Destructure an array; pack items into a variable with rest.

```js
const array = [1,2,3,4,5]
const [...repack] = array
```

6. Destructure an object; pack remaining properties with rest.

```js
const myObj = {
    name: 'object',
    shape: 'hotdog',
    color: 'honking red'
}

const { name, ...restProps } = myObj
```

7. Spread an object into another object.

```js
const obj1 = {
    head: true,
    arms: 2,
}

const obj2 = {
    legs: 2,
    ...obj1
}
```
[Back to top](#Module-8-Solutions)

## 09 - Useful array methods

***Try completing these exercises with the following set of data:***

```js
const people = [
  { firstName: 'Benjamin', lastName: 'Franklin', yearBorn: 1706, yearOfDeath: 1790 },
  { firstName: 'Thomas', lastName: 'Edison', yearBorn: 1847, yearOfDeath: 1931 },
  { firstName: 'Franklin', lastName: 'Roosevelt', yearBorn: 1882, yearOfDeath: 1945 },
  { firstName: 'Napolean', lastName: 'Bonaparte', yearBorn: 1769, yearOfDeath: 1821 },
  { firstName: 'Abraham', lastName: 'Lincoln', yearBorn: 1809, yearOfDeath: 1865 },
  { firstName: 'Mahatma', lastName: 'Gandhi', yearBorn: 1869, yearOfDeath: 1948 },
  { firstName: 'Winston', lastName: 'Churchill', yearBorn: 1874, yearOfDeath: 1965 },
  { firstName: 'Charles', lastName: 'Darwin', yearBorn: 1809, yearOfDeath: 1882 },
  { firstName: 'Albert', lastName: 'Einstein', yearBorn: 1879, yearOfDeath: 1955 },
  { firstName: 'Pablo', lastName: 'Picasso', yearBorn: 1881, yearOfDeath: 1973 },
  { firstName: 'Ludwig', lastName: 'Beethoven', yearBorn: 1770, yearOfDeath: 1827 },
  { firstName: 'Walt', lastName: 'Disney', yearBorn: 1901, yearOfDeath: 1966 },
  { firstName: 'Henry', lastName: 'Ford', yearBorn: 1863, yearOfDeath: 1947 },
  { firstName: 'Steve', lastName: 'Jobs', yearBorn: 1955, yearOfDeath: 2012 }
]
```

1. Find the index of `Thomas Edison`.

```js
const edisonIndex = people.findIndex(person => person.lastName.toLowerCase() === 'edison')
// => 1
```

2. Find the object that contains `Winston Churchill`.

```js
const winstonChurchill = people.find(person => person.lastName.toLowerCase() === 'churchill')
```

3. Create an array that contains people that died before 1940.

```js
const before1940 = people.filter(person => person.yearOfDeath < 1940)
```

4. Create an array that contains people that are alive between 1850 and 1970.

```js
const between = people.filter(person => {
    if (1850 < person.yearOfDeath && person.yearOfDeath < 1970) return true
})
```

5. Create an array that contains the `firstName`, `lastName` and `yearsLived` for each person (where `yearsLived` is the number of years the person lived).

```js
const subset = poeple.map(person => {
    return {
        firstName: person.firstName,
        lastName: person.lastName,
        yearsLived: person.yearOfDeath - person.yearBorn
    }
})
```

6. Get the total number of `yearsLived` of the people who were alive between 1750 and 1900.

```js
// define the methods to be used to make the nested array methods easier to read
// return true or false if the person object meets the criteria
const between = (person, min, max) => (min < person.yearOfDeath && person.yearOfDeath < 1900) ? true : false

// create an array out of the subset with just the yearsLived of each person
const yearsLivedSubset = (person) => {
    return {
        yearsLived: person.yearOfDeath - person.yearBorn
    }
}

// nested array method with a final call to reduce all the yearsLived into one value
const totalYearsLived = people.filter(person => between(person, 1750, 1900))
    .map(person => yearsLivedSubset(person))
    .reduce((accumulator, person) => accumulator + person.yearsLived
    ,0)
// 322 years
```

[Back to top](#Module-8-Solutions)

## 11 - Looping through objects

1. Loop through an array created with `Object.keys`

```js
const jsFrameworks = {
  google: 'Angular',
  facebook: 'React',
  other: 'Vue'
}

const keys = Object.keys(jsFrameworks)
console.log(keys)
```

2. Loop through an array created with `Object.values`

```js
const values = Object.values(jsFrameworks)
console.log(values)
```
3. Loop through an array created with `Object.entries`

```js
const entries = Object.entries(jsFrameworks)
console.log(entries)
```

[Back to top](#Module-8-Solutions)

## 12 - Implicit return object

```js
const createObject = _ => ({prop: 'value1', prop2: 'value2'})
createObject()
// Object { prop: "value1", prop2: "value2" }
```

[Back to top](#Module-8-Solutions)

[On to Module 9](../Module9/solutions.md)
