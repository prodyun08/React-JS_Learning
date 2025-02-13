# Destructing Arrays

In this here i will show 2 different way to assigning array items to a variable (old way / New way)
- old way
```js
const num = ['10', '20', '30'];

// old way
const a = num[0];
const b = num[1];
const c = num[2];
```
- new way
```js
const num = ['10', '20', '30'];
const [a, b, c] = num;
```

যদি কোনো ক্ষেত্রে a & b value আমার দরকার নেই সুধুমাত্র c এর value দরকার আছে এই ক্ষেত্রে আমি এই code run করতে পারি - 
```js
const num = ['10','20','30'];
const [,,c] = num; // Output : 30
```
just comma use করে আপনি `a,b` থেকে leave out করতে পারেন। 


### Basic Object Destructuring
```js
const student = {
    name: "Prodyun Biswas",
    age: 21,
    course: "Civil Engineering",
    skills: ["AutoCAD", "Revit", "STAAD Pro"]
};

// Destructuring the object
const { name, age, course, skills } = student;

console.log(name);  // Output: Prodyun Biswas
console.log(age);   // Output: 21
console.log(course); // Output: Civil Engineering
console.log(skills); // Output: ["AutoCAD", "Revit", "STAAD Pro"]
```

### Destructuring with Default Values
```js
const student = {
    name: "Prodyun Biswas",
    age: 21
};

// Assign default value if the property doesn't exist
const { name, age, course = "Not Assigned" } = student;

console.log(course); // Output: Not Assigned
```

### Destructuring with Alias (Renaming Variables)
```js
const student = {
    fullName: "Prodyun Biswas",
    age: 21,
    branch: "Civil"
};

// Renaming while destructuring
const { fullName: studentName, age: studentAge, branch: department } = student;

console.log(studentName);  // Output: Prodyun Biswas
console.log(studentAge);   // Output: 21
console.log(department);   // Output: Civil
```

### Destructuring Nested Objects
```js
const student = {
    name: "Prodyun Biswas",
    address: {
        city: "Kolkata",
        state: "West Bengal",
        country: "India"
    }
};

// Destructuring nested objects
const { address: { city, state, country } } = student;

console.log(city);   // Output: Kolkata
console.log(state);  // Output: West Bengal
console.log(country); // Output: India
```

### Destructuring Function Parameters
```js
const displayStudent = ({ name, age, skills }) => {
    console.log(`Name: ${name}, Age: ${age}`);
    console.log(`Skills: ${skills.join(", ")}`);
};

const student = {
    name: "Prodyun Biswas",
    age: 21,
    skills: ["AutoCAD", "Revit", "STAAD Pro"]
};

displayStudent(student);
// Output:
// Name: Prodyun Biswas, Age: 21
// Skills: AutoCAD, Revit, STAAD Pro
```
