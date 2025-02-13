# Spread Operator
The JavaScript spread operator `(...)` allows us to quickly copy all or part of an existing array or object into another array or object.

```js
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];

document.write(numbersCombined);   //Output: 1,2,3,4,5,6
```

The spread operator is often used in combination with destructuring.

Assign the first and second items from `numbers` to variables and put the rest in an array:

```js
const numbesr = [1, 2, 3, 4, 5, 6];
const [one, two, ...rest] = numbers;

document.write(numbers);   //Output: 1,2,3,4,5,6
```
We can use the spread operator with objects too:
```js
const myVehicle = {
  brand: 'Ford',
  model: 'Mustang',
  color: 'red'
}

const updateMyVehicle = {
  type: 'car',
  year: 2021, 
  color: 'yellow'
}

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle}

//Check the result object in the console:
console.log(myUpdatedVehicle);

//Open console and check object value.
```
