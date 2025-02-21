# React Class Components


## React Components

কম্পোনেন্ট হল independent এবং reusable কোডের ছোট ছোট অংশ। এগুলি JavaScript functions এর মতো কাজ করে, কিন্তু আলাদাভাবে execute হয় এবং `render()` function এর মাধ্যমে HTML return করে।

Components দুই ধরনের হয়: **Class Components** এবং **Function Components**। এই চ্যাপ্টারে তুমি **Class Components** সম্পর্কে শিখবে।

## Create a Class Component
React কম্পোনেন্ট তৈরি করার সময়, কম্পোনেন্টের নাম অবশ্যই একটি **uppercase** letter দিয়ে শুরু হতে হবে।

কম্পোনেন্টটিতে অবশ্যই `extends React.Component` স্টেটমেন্ট থাকতে হবে। এই স্টেটমেন্টটি **React.Component** এর inheritance তৈরি করে এবং কম্পোনেন্টকে **React.Component** এর ফাংশনগুলোর অ্যাক্সেস দেয়।

কম্পোনেন্টের একটি **`render()`** method থাকতে হবে, যা HTML return করে।


*Create a Class component called Car*

```js
// এই Class Component টি Car নামে তৈরি করা হয়েছে, যা React.Component কে extend করেছে।

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

🔹 render() method টি HTML return করে, যা এখানে <h2> ট্যাগের মধ্যে "Hi, I am a Car!" দেখাবে।

```

এখন তোমার React অ্যাপ্লিকেশনে **`Car`** নামে একটি কম্পোনেন্ট রয়েছে, যা একটি **`<h2>`** element return করে।
তোমার অ্যাপ্লিকেশনে এই কম্পোনেন্ট ব্যবহার করতে চাইলে, সাধারণ **HTML** এর মতো **syntax** ব্যবহার করতে হবে:  

```jsx
<Car />
```

*Display the Car component in the "root" element:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<Car />);
```

## **Component Constructor**  
যদি তোমার কম্পোনেন্টে একটি **`constructor()`** function থাকে, তাহলে এটি কম্পোনেন্ট **initialize** হওয়ার সময় **call** হবে।  

🔹 **Constructor** ফাংশনের কাজ:  
- কম্পোনেন্টের **properties** initialize করা।  
- **React**-এ কম্পোনেন্টের **properties** একটি **state** অবজেক্টের মধ্যে রাখা হয়।  
- **`super()`** ব্যবহার করে parent component (**React.Component**) এর **constructor** call করতে হয়, যাতে কম্পোনেন্ট **parent component-এর functions** অ্যাক্সেস করতে পারে।  

---

### **Car Component এ Constructor Function যোগ করা:**  

```jsx
class Car extends React.Component {
  constructor() {
    super();
    this.state = { color: "red" };
  }
  render() {
    return <h2>I am a Car!</h2>;
  }
}
```

এখানে **`this.state = { color: "red" }`** দ্বারা **state** তৈরি করা হয়েছে, যেখানে **color** property এর মান `"red"`।

---

### **State এর মান render() ফাংশনে ব্যবহার করা:**  

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  constructor() {
    super();
    this.state = { color: "red" };
  }
  render() {
    return <h2>I am a {this.state.color} Car!</h2>;
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

🔹 **এই কোডের আউটপুট হবে:**  
✅ **"I am a red Car!"**  

এখানে **`this.state.color`** ব্যবহার করে **state** থেকে **color** মানটি নেওয়া হয়েছে এবং **render()** ফাংশনের মধ্যে **return** করা হয়েছে। 🚗

## **Props (প্রপস)**
**Props** হল **component properties** হ্যান্ডেল করার আরেকটি উপায়।  
Props হল **function arguments**-এর মতো, যা **attributes** হিসাবে **component**-এ পাঠানো হয়।

**Example:**  
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.color} Car!</h2>;
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car color="red"/>);
```
এখানে `color="red"` **props** হিসাবে **Car component**-এ পাঠানো হয়েছে।

---

## **Props in the Constructor (Constructor এ Props ব্যবহার)**
যদি কম্পোনেন্টে **constructor function** থাকে, তাহলে **props** অবশ্যই **constructor()**-এ **pass** করতে হবে এবং **super(props)** ব্যবহার করতে হবে।

**Example:**  
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return <h2>I am a {this.props.model}!</h2>;
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car model="Mustang"/>);
```
এখানে `model="Mustang"` props হিসাবে পাঠানো হয়েছে এবং `this.props.model` দ্বারা **render()** মেথডে ব্যবহার করা হয়েছে।

---

## **Components in Components (এক কম্পোনেন্টের ভেতর আরেকটি কম্পোনেন্ট)**
React-এ আমরা **একটি কম্পোনেন্টের ভিতরে অন্য কম্পোনেন্ট ব্যবহার** করতে পারি।

### **Example:**  
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  render() {
    return <h2>I am a Car!</h2>;
  }
}

class Garage extends React.Component {
  render() {
    return (
      <div>
        <h1>Who lives in my Garage?</h1>
        <Car />
      </div>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
এখানে **Garage** কম্পোনেন্টের মধ্যে **Car** কম্পোনেন্টকে **use** করা হয়েছে।

---

## **Components in Files (কম্পোনেন্ট আলাদা ফাইলে রাখা)**
React-এ কোড **re-use** করার জন্য, আমরা কম্পোনেন্টগুলো **অন্য ফাইলে সংরক্ষণ** করতে পারি।

### **Step 1: `Car.js` ফাইল তৈরি করুন**
```jsx
import React from 'react';

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

export default Car;
```
এখানে **`export default Car;`** দ্বারা **Car component** অন্য ফাইলে **import** করা যাবে।

### **Step 2: `App.js` বা প্রধান ফাইলে `Car.js` ইমপোর্ট করা**
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
এতে **Car.js**-এ তৈরি কম্পোনেন্ট **import** করে ব্যবহার করা হয়েছে।

---

## **React Class Component State (State কীভাবে কাজ করে)**
React **Class Component**-এ একটি **built-in state object** থাকে, যেখানে কম্পোনেন্টের ডেটা সংরক্ষণ করা হয়।  
যখন **state পরিবর্তন হয়**, তখন কম্পোনেন্ট **re-render** হয়।

---

### **Creating the state Object (State তৈরি করা)**
```jsx
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = { brand: "Ford" };
  }
  render() {
    return (
      <div>
        <h1>My Car</h1>
      </div>
    );
  }
}
```
এখানে **state object**-এ `"brand": "Ford"` সংরক্ষণ করা হয়েছে।

---

### **Multiple Properties in State (State-এ একাধিক মান রাখা)**
```jsx
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  render() {
    return (
      <div>
        <h1>My Car</h1>
      </div>
    );
  }
}
```
এখানে **state**-এ **brand, model, color, year** সংরক্ষণ করা হয়েছে।

---

### **Using the State Object (State-কে UI-তে দেখানো)**
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
  }
  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color} {this.state.model} from {this.state.year}.
        </p>
      </div>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
🔹 **Output:**  
✅ `My Ford`  
✅ `It is a red Mustang from 1964.`  

এখানে **state-এর মান `this.state.propertyname`** ব্যবহার করে দেখানো হয়েছে।

----
## Changing the state Object

স্টেট অবজেক্টের মান পরিবর্তন করতে this.setState() মেথড ব্যবহার করা হয়

যখন state অবজেক্টের কোনো মান পরিবর্তিত হয়, তখন component পুনরায় render হয় এবং আউটপুট নতুন মান অনুযায়ী পরিবর্তিত হয়


একটি **button** যোগ করো, যার **onClick event** থাকবে, যা **color property** পরিবর্তন করবে।  

```jsx
class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      brand: "Ford",  // গাড়ির ব্র্যান্ড
      model: "Mustang", // গাড়ির মডেল
      color: "red", // গাড়ির রঙ
      year: 1964 // গাড়ির বছর
    };
  }

  // রঙ পরিবর্তনের জন্য ফাংশন (Function to change color)
  changeColor = () => {
    this.setState({color: "blue"}); // নতুন রঙ সেট করা হচ্ছে
  }

  render() {
    return (
      <div>
        <h1>My {this.state.brand}</h1>
        <p>
          It is a {this.state.color} {this.state.model} from {this.state.year}.
        </p>
        {/* Change color বাটন */}
        <button
          type="button"
          onClick={this.changeColor}
        >Change color</button>
      </div>
    );
  }
}
```

🔹 এই **component**-এ যখন **Change color** বাটনে ক্লিক করা হবে, তখন **state পরিবর্তিত হবে**, এবং **UI নতুন color দেখাবে!** 🚀🔥

**🔹 Always use `setState()` method** React এ **state পরিবর্তন করার জন্য সবসময় `setState()` method ব্যবহার করা উচিত।**  
এটি নিশ্চিত করে যে **component বুঝতে পারবে যে state আপডেট হয়েছে**, এবং **`render()` method সহ অন্যান্য lifecycle methods** পুনরায় চলবে।  

#### ⚡ **উদাহরণ (Example):**  
```jsx
this.setState({ color: "blue" }); // ✅ সঠিক পদ্ধতি  
this.state.color = "blue"; // ❌ ভুল পদ্ধতি  
```
**❌ `this.state.color = "blue"` সরাসরি পরিবর্তন করলে React বুঝতে পারবে না, ফলে UI আপডেট হবে না।**  
**✅ `setState()` ব্যবহার করলে React state পরিবর্তন বুঝতে পারবে এবং UI আপডেট করবে।** 🚀

----

## Lifecycle of Components

React-এ প্রত্যেকটি component-এর একটি lifecycle থাকে, যা আমরা monitor এবং manipulate করতে পারি।

এই lifecycle-এর তিনটি প্রধান ধাপ (Three Main Phases) আছে:
1️⃣ Mounting (প্রাথমিক লোড হওয়া) - Component প্রথমবার DOM-এ যুক্ত হয়।
2️⃣ Updating (আপডেট হওয়া) - State বা props পরিবর্তিত হলে Component রি-রেন্ডার হয়।
3️⃣ Unmounting (সরিয়ে ফেলা) - Component DOM থেকে মুছে ফেলা হয়।


## Mounting
Mounting মানে Component-কে DOM-এ যুক্ত করা। যখন কোনো Component প্রথমবার DOM-এ আসে, তখন React চারটি built-in method sequentially execute করে।

✅ Mounting-এর চারটি ধাপ:
1️⃣ constructor() → Component-এর state এবং properties initialize করার জন্য।
2️⃣ getDerivedStateFromProps() → Props থেকে নতুন state সেট করতে হলে এই method ব্যবহার করা হয়।
3️⃣ render() → Component-এর UI (JSX) রেন্ডার করার জন্য।
4️⃣ componentDidMount() → Component DOM-এ যুক্ত হওয়ার পর একবারই execute হয়। API calls বা DOM manipulation এখানে করা হয়।

⚠️ render() method বাধ্যতামূলক, অন্যগুলো অপশনাল।

----
## constructor

🔸 **constructor() method** হল প্রথম method যা React component তৈরি হওয়ার সময় **সবচেয়ে আগে execute হয়**। এটি মূলত **initial state এবং initial values সেট করার জন্য** ব্যবহৃত হয়।  

✅ **constructor() method-এর গুরুত্বপূর্ণ বৈশিষ্ট্য:**  
1️⃣ **Component তৈরি হওয়ার সাথে সাথেই call হয়।**  
2️⃣ **State ও props initialize করার জন্য ব্যবহার করা হয়।**  
3️⃣ **super(props) ব্যবহার করা বাধ্যতামূলক,** কারণ এটি parent class (React.Component)-এর constructor inherit করতে সাহায্য করে।  
4️⃣ **Direct state assignment (this.state = {...}) শুধুমাত্র constructor-এর ভেতরেই করা যায়।**  


### **🚀 Example: Using constructor()**
```jsx
import React from "react";
import ReactDOM from "react-dom";

class Car extends React.Component {
  constructor(props) {
    super(props); // Always call super(props) first
    this.state = { brand: "Ford", color: "red" }; // Initial state
  }

  render() {
    return (
      <div>
        <h1>My Car Brand: {this.state.brand}</h1>
        <p>Color: {this.state.color}</p>
      </div>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Car />);
```
📌 **এখানে,** আমরা **constructor() method-এ state সেট করেছি, এবং render() method-এ সেই state UI-তে দেখাচ্ছি।**  

⚠️ **Tip:** যদি state বা props ব্যবহার না করতে হয়, তাহলে **constructor() method না দিলেও Component কাজ করবে!** 🚀

----
## getDerivedStateFromProps


📌 **getDerivedStateFromProps() method** হলো একটি **static lifecycle method** যা **render() method-এর ঠিক আগে call হয়।** এটি props অনুযায়ী state update করার জন্য ব্যবহৃত হয়।  

✅ **এই method-এর গুরুত্বপূর্ণ বৈশিষ্ট্য:**  
1️⃣ **render() method-এর আগে call হয়।**  
2️⃣ **Props অনুযায়ী state update করতে ব্যবহৃত হয়।**  
3️⃣ **এটি static হওয়ায়, this ব্যবহার করা যায় না।**  
4️⃣ **Method টি সরাসরি state update করতে পারে না, বরং একটি নতুন state object return করে।**  



### **🚀 Example: Using getDerivedStateFromProps()**
```jsx
import React from "react";
import ReactDOM from "react-dom";

class Car extends React.Component {
  constructor(props) {
    super(props);
    this.state = { favoriteColor: "red" };
  }

  static getDerivedStateFromProps(props, state) {
    return { favoriteColor: props.favcol }; // Update state based on props
  }

  render() {
    return (
      <div>
        <h1>My Favorite Car Color is {this.state.favoriteColor}</h1>
      </div>
    );
  }
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Car favcol="blue" />);
```


✅ **constructor() method প্রথমে favoriteColor = "red" সেট করে।**  
✅ **getDerivedStateFromProps() method props থেকে নতুন color ("blue") সেট করে।**  
✅ **render() method updated state দেখায়।**  

⚠️ **Tip:**  
👉 যদি এই method থেকে `null` return করা হয়, তাহলে state পরিবর্তন হবে না। 🚀




