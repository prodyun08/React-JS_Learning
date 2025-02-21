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
Put the shoot function inside the Football component:

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

