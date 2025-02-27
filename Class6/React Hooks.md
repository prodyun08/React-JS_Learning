## React Hooks  

React-এর **version 16.8**-এ Hooks যুক্ত করা হয়েছিল।  

Hooks-এর মাধ্যমে **function components**-এ **state** এবং অন্যান্য React ফিচার ব্যবহার করা যায়। তাই এখন সাধারণত **class components** ব্যবহারের প্রয়োজন হয় না।  

যদিও Hooks সাধারণত class components-কে রিপ্লেস করে, তবে React থেকে **class components সম্পূর্ণরূপে সরিয়ে ফেলার কোনো পরিকল্পনা নেই।**  

---  

### **Hook কী?**  
Hooks-এর মাধ্যমে আমরা React-এর **state এবং lifecycle methods**-এ **"hook"** করতে পারি।  

#### **উদাহরণ:**  
নিচে একটি **Hook**-এর উদাহরণ দেওয়া হলো। যদি পুরোপুরি বুঝতে না পারেন, চিন্তার কিছু নেই! পরবর্তী সেকশনে বিস্তারিত আলোচনা করা হবে।  

```jsx
import React, { useState } from "react";
import ReactDOM from "react-dom/client";

function FavoriteColor() {
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My favorite color is {color}!</h1>
      <button type="button" onClick={() => setColor("blue")}>Blue</button>
      <button type="button" onClick={() => setColor("red")}>Red</button>
      <button type="button" onClick={() => setColor("pink")}>Pink</button>
      <button type="button" onClick={() => setColor("green")}>Green</button>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<FavoriteColor />);
```

**React Hooks ব্যবহারের জন্য react থেকে import করতে হবে।**  

এখানে আমরা **useState Hook** ব্যবহার করছি **state track** করার জন্য।  

👉 **State সাধারণত এমন ডাটা বা প্রপার্টি বোঝায়, যা অ্যাপ্লিকেশনের মধ্যে পরিবর্তনশীল।**  

---  

### **Hook ব্যবহারের নিয়ম (Hook Rules)**  
Hooks ব্যবহারের **৩টি গুরুত্বপূর্ণ নিয়ম** রয়েছে:  

1️⃣ **Hooks শুধুমাত্র React function components-এর ভিতরে ব্যবহার করা যাবে।**  
2️⃣ **Hooks শুধুমাত্র কম্পোনেন্টের টপ-লেভেলে কল করা যাবে।**  
3️⃣ **Hooks কন্ডিশনালভাবে (if-else, loop-এর ভিতরে) কল করা যাবে না।**  

📌 **Note:** React class components-এ Hooks কাজ করবে না।  

---  

### **Custom Hooks (কাস্টম হুকস)**  
যদি **stateful logic** একাধিক কম্পোনেন্টে **পুনরায় ব্যবহার (reusable)** করতে হয়, তাহলে আমরা **নিজস্ব Custom Hooks তৈরি** করতে পারি।  

📌 Custom Hooks সম্পর্কে বিস্তারিত আমরা **Custom Hooks সেকশনে** আলোচনা করবো।