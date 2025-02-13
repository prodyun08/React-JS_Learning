# Spread Operator
The JavaScript spread operator `(...)` allows us to quickly copy all or part of an existing array or object into another array or object.

```js
const numbersOne = [1, 2, 3];
const numbersTwo = [4, 5, 6];
const numbersCombined = [...numbersOne, ...numbersTwo];

document.write(numbersCombined);   //Output: 1,2,3,4,5,6
```

The spread operator is often used in combination with destructuring.

Assign the first and second items from numbers to variables and put the rest in an array:

```js
const numbesr = [1, 2, 3, 4, 5, 6];
const [one, two, ...rest] = numbers;

document.write(numbers);   //Output: 1,2,3,4,5,6
```
