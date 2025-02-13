# Array Methods in React

There are many JavaScript array methods.

- 🔹 1. `map()` → Transform Array Elements
Used to iterate over an array and return a new array.
```js
const names = ["John", "Alice", "Bob"];

function NameList() {
  return (
    <ul>
      {names.map((name, index) => (
        <li key={index}>{name}</li>
      ))}
    </ul>
  );
}
```
Use Case:
✅ Rendering lists in JSX (React requires a key prop for list items).



- 🔹 2. `filter()` → Remove Elements Based on Condition
Creates a new array with elements that pass a test.
```js
const numbers = [10, 15, 20, 25, 30];
const evenNumbers = numbers.filter(num => num % 2 === 0);

console.log(evenNumbers); // Output: [10, 20, 30]
```
Use Case:
✅ Removing unwanted items (e.g., filtering completed tasks in a Todo App).


- 🔹 3. `find()` → Get First Matching Element
Returns the first element that satisfies a condition.
```js
const users = [
  { id: 1, name: "John" },
  { id: 2, name: "Alice" },
];

const user = users.find(user => user.id === 2);
console.log(user); // Output: { id: 2, name: "Alice" }
```
Use Case:
✅ Fetching specific data (e.g., getting a user by ID).



- 🔹 4. `some()` → Check If Any Element Matches Condition
Returns true if at least one element matches the condition.
```js
const users = [
  { name: "John", role: "user" },
  { name: "Alice", role: "admin" },
];

const hasAdmin = users.some(user => user.role === "admin");
console.log(hasAdmin); // Output: true
```
Use Case:
✅ Checking if an item exists in an array.


- 🔹 5. `every()` → Check If All Elements Match Condition
Returns true only if all elements satisfy a condition.
```js
const users = [
  { name: "John", active: true },
  { name: "Alice", active: true },
];

const allActive = users.every(user => user.active);
console.log(allActive); // Output: true
```
Use Case:
✅ Validating if all elements meet a requirement.



- 🔹 6. `reduce()` → Accumulate Values
Reduces an array to a single value.
```js
const cart = [
  { item: "Shoes", price: 50 },
  { item: "Shirt", price: 30 },
];

const total = cart.reduce((sum, product) => sum + product.price, 0);
console.log(total); // Output: 80
```
Use Case:
✅ Summing values (e.g., total price in a shopping cart).


- 🔹 7. `sort()` → Sort an Array
Sorts an array in place.
```js
const numbers = [5, 2, 8, 1, 3];
numbers.sort((a, b) => a - b);
console.log(numbers); // Output: [1, 2, 3, 5, 8]
```
Use Case:
✅ Sorting lists (e.g., sorting products by price).



- 🔹 8. `concat()` → Merge Arrays
Combines two or more arrays.
```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const merged = arr1.concat(arr2);
console.log(merged); // Output: [1, 2, 3, 4, 5, 6]
```
Use Case:
✅ Merging multiple datasets.



- 🔹 9. `splice()` → Modify an Array (Add/Remove)
Modifies the original array.
```js
const items = ["Apple", "Banana", "Cherry"];
items.splice(1, 1); // Removes "Banana"
console.log(items); // Output: ["Apple", "Cherry"]
```
Use Case:
✅ Removing or inserting elements dynamically.



- 🔹 10. `slice()` → Extract Part of an Array
Returns a new array without modifying the original.
```js
const fruits = ["Apple", "Banana", "Cherry", "Date"];
const sliced = fruits.slice(1, 3);

console.log(sliced); // Output: ["Banana", "Cherry"]
```
Use Case:
✅ Getting a portion of data (e.g., pagination).



| Method    | Purpose | Modifies Original? |
|-----------|---------|-------------------|
| `map()`   | Transform elements | ❌ No |
| `filter()`| Remove elements | ❌ No |
| `find()`  | Find first matching element | ❌ No |
| `some()`  | Check if any element matches | ❌ No |
| `every()` | Check if all elements match | ❌ No |
| `reduce()`| Accumulate values | ❌ No |
| `sort()`  | Sort elements | ✅ Yes |
| `concat()`| Merge arrays | ❌ No |
| `splice()`| Add/Remove elements | ✅ Yes |
| `slice()` | Extract part of an array | ❌ No |

