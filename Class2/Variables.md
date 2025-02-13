# Variables 

JavaScript Version ES6 Update হওয়ার আগে শুধুমাত্র var keyward ব্যবহার করে Variables কে defining করা যেত।। যদি আপনি varibales কে defining না করেন তাহলে সেটি Global Object assigned করা হতো। এবং Variables Undefined & Error ভাবে ধরা হতো।

এখন ES6 এর মাধ্যমে 3টে উপায়ে varibales কে defining করা সম্ভব। : var, let & const.



| Keyword  | Scope           | Reassignment | Redeclaration | Hoisting Behavior        |
|----------|---------------|--------------|--------------|--------------------------|
| `var`    | Function-scoped | ✅ Yes       | ✅ Yes       | Hoisted with `undefined` |
| `let`    | Block-scoped   | ✅ Yes       | ❌ No        | Hoisted but uninitialized |
| `const`  | Block-scoped   | ❌ No        | ❌ No        | Hoisted but uninitialized |


#### 1.var
```js
var name = "John";  // Variable declaration
console.log(name); // Output : John
```

#### 2.let
```js
let age = 25;   // Variable declaration
console.log(age); // Output : 25
```

#### 3.const
```js
const PI = 3.1416;  // Declaring a constant
console.log(PI);  // Output: 3.1416
```

