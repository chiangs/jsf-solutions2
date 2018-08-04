# Module 9 Solutions

<!-- TOC -->

- [Module 9 Solutions](#module-9-solutions)
    - [03 - Reduce State Changes](#03---reduce-state-changes)
    - [04 - Don't reassign](#04---dont-reassign)
    - [07 - Preventing objects from mutating](#07---preventing-objects-from-mutating)
    - [08 - Preventing arrays from mutating](#08---preventing-arrays-from-mutating)

<!-- /TOC -->

[Back to Module 8](../Module8/solutions.md)

## 03 - Reduce State Changes

To reduce state changes, you prevent two things from happening:

1. reassignments
2. mutations

## 04 - Don't reassign

1. You should always declare variables with const. When you declare variables with const, you'll see the const keyword. It is a good indicator that the variable is created in the current scope; it will never change the external state.

2. If you need a if/else statement to determine what value your variable should take, consider using a ternary operator instead of an if/else statement.

3. If you need three or more if statements, consider writing a function that uses an early return. This makes your code more declarative as a result.

## 07 - Preventing objects from mutating

You can prevent objects from mutating through two methods:

    Object.assign
    assignment


1. Combine two objects with `Object.assign`.

```js
const car = {
    type: 'car',
    fueltype: 'gas',
    wheels: 4
}

const teslaOptions = {
    color: 'black',
    fueltype: 'electric'
}

const createVehicle = (baseObj, objOptions) => Object.assign({}, baseObj, objOptions)

const newTesla = createVehicle(car, teslaOptions)

console.log(newTesla)
// => color: "black", fueltype: "electric", type: "car", wheels: 4
```

2. Combine two objects with `assignment`.

```js
const car =  {
    vehicleType: {
        car: true
        class: 'c'
    },
    fueltype: 'gas',
    wheels: 4
}

const teslaOptions = {
    color: 'black',
    fueltype: 'electric',
    package: {
        trim: 'S',
        line: '95'
    }
}

const createVehicle = (baseObj, objOptions) => assignment({}, baseObj, objOptions)

const newTesla = createVehicle(car, teslaOptions)
```

## 08 - Preventing arrays from mutating

`Array.slice` - you tell JavaScript which parts of the array you want to copy out as your new array.

```js
const newArray = array.slice(startIndex, endIndex)

// omit indexes to get the entire array
const copyArray = array.slice();
```

`Array.concat` - combines 2 arrays to form a new one.

[Back to top](#Module-9-Solutions)

[On to Module 10](../Module19/solutions.md)