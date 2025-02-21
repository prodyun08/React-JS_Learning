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
