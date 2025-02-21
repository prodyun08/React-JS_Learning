# React Events
ঠিক যেমন HTML DOM events, React ও **user events** এর ভিত্তিতে action perform করতে পারে।  

React-এ HTML-এর মতোই **click, change, mouseover** ইত্যাদি events থাকে।  

উদাহরণস্বরূপ, একটি **button click event**:  

```jsx
function App() {  
  const handleClick = () => {  
    alert("Button Clicked!");  
  };

  return <button onClick={handleClick}>Click Me</button>;  
}

export default App;
```

এখানে, **onClick** event ব্যবহার করে **button click করলে** `handleClick` function চালানো হবে। React-এ event handling অনেকটা HTML-এর মতোই কাজ করে, কিন্তু এটি JSX syntax অনুসরণ করে।


## Adding Events
React events camelCase syntax format এ লেখা হয় :
onClick instead of onclick.

React event handlers curly braces ভিতরে লেখা হয় :
onClick={shoot}  instead of onclick="shoot()".

#### React
```jsx
<button onClick={shoot}>Take the Shot!</button>
```
#### Html
```html
<button onclick="shoot()">Take the Shot!</button>
```
#### Example 

*চলো Football component এর মধ্যে shoot function put করা যাক :*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Football() {
  const shoot = () => {
    alert("Great Shot!");
  }

  return (
    <button onClick={shoot}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```

✅ **যখন Take the shot Button এ click করব alert function work করবে এবং popup এ Great Shot! message show করবে।**

## Passing Arguments
event handler এর মধ্যে argument pass করা হোক arrow function ব্যবহার করে। 
#### Example:
Send "Goal!" as a parameter to the shoot function, using arrow function:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Football() {
  const shoot = (a) => {
    alert(a);
  }

  return (
    <button onClick={() => shoot("Goal!")}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```

## React Event Object
Event handlers have access to the React event that triggered the function.

In our example the event is the "click" event.

#### Example:
Arrow Function: Sending the event object manually:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Football() {
  const shoot = (a, b) => {
    alert(b.type);
		/*
		'b' represents the React event that triggered the function.
    In this case, the 'click' event
		*/
  }

  return (
    <button onClick={(event) => shoot("Goal!", event)}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```
