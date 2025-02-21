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

## Props

Another way of handling component properties is by using `props`.

Props are like function arguments, and you send them into the component as attributes.

You will learn more about `props` in the next chapter.


*Use an attribute to pass a color to the Car component, and use it in the render() function:*

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.color} Car!</h2>;
  }
}

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<Car color="red"/>);
```

## Props in the Constructor
If your component has a constructor function, the props should always be passed to the constructor and also to the React.Component via the `super()` method.

##### Example 
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
## Components in Components

We can refer to components inside other components:

*Use the Car component inside the Garage component:*

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

## Components in Files

React is all about re-using code, and it can be smart to insert some of your components in separate files.

To do that, create a new file with a `.js` file extension and put the code inside it:

Note that the file must start by importing React (as before), and it has to end with the statement `export default Car;`.

*This is the new file, we named it Car.js:*

```js
import React from 'react';

class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

export default Car;
```
To be able to use the `Car` component, you have to import the file in your application.

*Now we import the `Car.js` file in the application, and we can use the `Car` component as if it was created here.*

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<Car />);
```
## React Class Component State
React Class components have a built-in `state` object.

You might have noticed that we used `state` earlier in the component constructor section.

The `state` object is where you store property values that belongs to the component.

When the `state` object changes, the component re-renders.

## Creating the state Object
The state object is initialized in the constructor:

*Specify the state object in the constructor method:*

```js
class Car extends React.Component {
  constructor(props) {
    super(props);
  this.state = {brand: "Ford"};
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
The state object can contain as many properties as you like:

*Specify all the properties your component need:*
```js
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
## Using the `state` Object
Refer to the `state` object anywhere in the component by using the `this.state.propertyname` syntax:

*Refer to the `state` object in the `render()` method:*
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
          It is a {this.state.color}
          {this.state.model}
          from {this.state.year}.
        </p>
      </div>
    );
  }
}

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);
root.render(<Car />);
```
## Changing the state Object




