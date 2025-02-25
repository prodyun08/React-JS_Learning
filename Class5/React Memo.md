# React Memo

`React.memo()` হল একটি **higher-order component (HOC)**, যা **প্রপস পরিবর্তন না হলে কম্পোনেন্ট পুনরায় রেন্ডার হওয়া এড়িয়ে যায়।** এটি পারফরম্যান্স উন্নত করতে সাহায্য করে।  

---

## ❌ **Problem: Unnecessary Re-rendering**  

```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";
import Todos from "./Todos";

const App = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState(["todo 1", "todo 2"]);

  const increment = () => {
    setCount((c) => c + 1);
  };

  return (
    <>
      <Todos todos={todos} />
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
      </div>
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

👉 **`Todos` কম্পোনেন্ট বারবার রেন্ডার হচ্ছে**, যদিও `todos` প্রপস পরিবর্তন হচ্ছে না।  

---

### **🔍 Issue in `Todos.js`**
```jsx
const Todos = ({ todos }) => {
  console.log("child render");
  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => (
        <p key={index}>{todo}</p>
      ))}
    </>
  );
};

export default Todos;
```
📌 **প্রতি বার `increment` বাটন ক্লিক করলে `Todos` কম্পোনেন্টও রেন্ডার হয়!**  

---

## ✅ **Solution: Use `React.memo()`**  

👉 `Todos` কম্পোনেন্টকে `memo()` দিয়ে **wrap** করলে, এটি শুধুমাত্র তখনই রেন্ডার হবে যখন **প্রপস পরিবর্তন হবে।**  

### **✔ Optimized `Todos.js`**
```jsx
import { memo } from "react";

const Todos = ({ todos }) => {
  console.log("child render"); // Logs only when `todos` updates
  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => (
        <p key={index}>{todo}</p>
      ))}
    </>
  );
};

// Wrap with React.memo to prevent unnecessary re-renders
export default memo(Todos);
```

---

## 🛠 **How `React.memo()` Works**
1. ✅ `memo()` ফাংশন **প্রপস চেক করে** → যদি আগের ও বর্তমান প্রপস একই থাকে, তাহলে **কম্পোনেন্ট রি-রেন্ডার হবে না।**  
2. ✅ `increment` বাটন ক্লিক করলে এখন **শুধু `count` আপডেট হবে**, `Todos` কম্পোনেন্ট **রেন্ডার হবে না!** 🎯  

