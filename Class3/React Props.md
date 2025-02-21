# React Props
- Props হল React components পাঠানো arguments.
- Props HTML attributes মাধ্যমে components passed করা হয়।

*props stands for properties.*

---
👉 **Props হল React Component-এ data পাঠানোর উপায়।**  
👉 **JavaScript-এর function arguments এবং HTML attributes-এর মতো কাজ করে।**  
👉 **Parent Component থেকে Child Component-এ Props পাঠানো হয়।**  


### **🛠 Example: How to Use Props**
```jsx
function Car(props) {
  return <h2>I am a {props.brand}!</h2>;
}

function Garage() {
  return (
    <div>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" /> 
    </div>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Garage />);
```

✅ **Garage Component → `Car` Component-এ `brand="Ford"` Props পাঠাচ্ছে।**  
✅ **Car Component `props.brand` ব্যবহার করে "I am a Ford!" print করছে।**  

### **🔹 Multiple Props ব্যবহার করা**
```jsx
function Car(props) {
  return <h2>I have a {props.brand}, Model: {props.model}!</h2>;
}

function Garage() {
  return (
    <div>
      <Car brand="Toyota" model="Corolla" />
    </div>
  );
}
```
✅ **এখানে `props.brand → "Toyota"` এবং `props.model → "Corolla"` পাঠানো হয়েছে।**  

---

### **🔹 Object আকারে Props পাঠানো**
```jsx
function Car(props) {
  return <h2>I am a {props.carInfo.brand}, Model: {props.carInfo.model}!</h2>;
}

function Garage() {
  const car = { brand: "Tesla", model: "Model X" };
  return (
    <div>
      <Car carInfo={car} />
    </div>
  );
}
```
✅ **Props `carInfo` নামে object আকারে পাঠানো হয়েছে এবং `Car` Component-এ ব্যবহার করা হয়েছে।**  


## Pass Data
Props হল এমন একটি method, যার মাধ্যমে আপনি one component থেকে another component-এ data pass করতে পারেন, just like parameters in a function.

*Send the "brand" property from the Garage component to the Car component:*

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

function Garage() {
  return (
    <>
	    <h1>Who lives in my garage?</h1>
	    <Car brand="Ford" />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

যদি আপনার কাছে একটি variable থাকে যা send করতে চান, এবং উপরের example-এর মতো string না হয়, তাহলে আপনি শুধু সেই variable-এর name টি curly brackets `{}` এর মধ্যে রাখতে পারেন।

একটি variable carName তৈরি করুন এবং এটি Car component-এ পাঠান:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

function Garage() {
  const carName = "Ford";
  return (
    <>
	    <h1>Who lives in my garage?</h1>
	    <Car brand={ carName } />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
এখানে carName নামে একটি variable তৈরি করা হয়েছে এবং সেটি Car component-এ props আকারে পাঠানো হয়েছে।

**Or if it was an object:**

একটি object carInfo তৈরি করুন এবং এটি Car component-এ props হিসেবে পাঠান:
```
jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <h2>I am a { props.brand.model }!</h2>;
}

function Garage() {
  const carInfo = { name: "Ford", model: "Mustang" };
  return (
    <>
	    <h1>Who lives in my garage?</h1>
	    <Car brand={ carInfo } />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
**Note:** React Props হলো **read-only**! আপনি যদি তাদের মান পরিবর্তন করতে চেষ্টা করেন, তাহলে **error** পাবেন।  

উদাহরণস্বরূপ, নিচের কোডটি error দেবে, কারণ props-এর মান পরিবর্তন করা হচ্ছে:  

```jsx
function Car(props) {  
  props.info.brand = "Honda"; // ❌ This will cause an error!
  return <h2>Car Brand: {props.info.brand}</h2>;  
}

export default Car;
```

React-এ props immutable (পরিবর্তনযোগ্য নয়), তাই আপনি তাদের মান সরাসরি পরিবর্তন করতে পারবেন না। যদি পরিবর্তন করতে হয়, তাহলে **useState** বা **parent component থেকে নতুন props পাঠানোর মাধ্যমে** পরিবর্তন করতে হবে।
