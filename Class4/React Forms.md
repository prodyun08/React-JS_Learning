# React Forms
### 📝 React Forms (React ফর্ম)  

Just like in HTML, **React uses forms** (React-এ ফর্ম ব্যবহার করা হয় যাতে ইউজাররা ওয়েব পেজের সাথে ইন্টারঅ্যাক্ট করতে পারে)।  

---

### 🛠 Adding Forms in React (React-এ ফর্ম যোগ করা)  

আপনি **React-এ ফর্ম** (form) HTML-এর মতোই অ্যাড করতে পারেন। নিচের উদাহরণটি দেখুন:  

### 📌 Example (উদাহরণ):  
এই ফর্মটি ইউজারকে তার নাম এন্টার করতে দেবে।  

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function MyForm() {
  return (
    <form>
      <label>Enter your name:
        <input type="text" />
      </label>
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

এখানে:  
- `<form>` (HTML ফর্ম ট্যাগ) ব্যবহার করা হয়েছে।  
- `<label>` ইউজারের জন্য একটি লেবেল তৈরি করে।  
- `<input type="text" />` ইউজার ইনপুট নেওয়ার জন্য ব্যবহার করা হয়।  
- **ReactDOM.createRoot()** `root` আইডি থাকা **HTML element**-এ রেন্ডার করে।  

এই কোডটি সরাসরি **React App**-এ রান করালে ইউজার তার নাম ইনপুট করতে পারবে। 🚀  


### 🚀 React Forms: Preventing Default Behavior (ডিফল্ট বিহেভিয়ার প্রতিরোধ)  

এই ফর্মটি **নরমালভাবে কাজ করবে**, **ফর্ম সাবমিট হবে** এবং **পেজ রিফ্রেশ হবে**।  

🔴 **কিন্তু** React-এ সাধারণত আমরা চাই না যে ফর্ম সাবমিটের পরে পেজ রিফ্রেশ হোক।  

💡 **React-এ আমরা চাই** যে ব্রাউজারের ডিফল্ট ফর্ম সাবমিট করার প্রক্রিয়াটি বন্ধ করা হোক এবং **React ফর্মটি নিয়ন্ত্রণ করুক**।  

👉 এজন্য **`event.preventDefault()`** ব্যবহার করা হয়।  

📌 **পরবর্তী ধাপে আমরা দেখবো কিভাবে এটি ইমপ্লিমেন্ট করা হয়!** 🚀

### 🎯 Handling Forms in React (React-এ ফর্ম হ্যান্ডলিং)  

ফর্ম হ্যান্ডলিং মানে হলো **ফর্মের ডাটা কিভাবে পরিবর্তিত হয় বা সাবমিট হলে কিভাবে পরিচালিত হবে**।  

---

### 🆚 HTML vs React Form Handling  
✅ **HTML-এ** ফর্ম ডাটা সাধারণত **DOM দ্বারা পরিচালিত হয়**।  
✅ **React-এ** ফর্ম ডাটা সাধারণত **কম্পোনেন্ট দ্বারা পরিচালিত হয়**।  
✅ **React-এ কম্পোনেন্ট ডাটা ম্যানেজ করলে, সমস্ত ডাটা state-এ সংরক্ষণ করা হয়**।  

---

### 🚀 Controlled Component (কন্ট্রোলড কম্পোনেন্ট)  

👉 **React-এ ইনপুট পরিবর্তন নিয়ন্ত্রণ করতে `onChange` event ব্যবহার করা হয়**।  
👉 **`useState` Hook ব্যবহার করে ইনপুটের মান সংরক্ষণ করা যায়**।  
👉 **এটি "single source of truth" হিসেবে কাজ করে** পুরো অ্যাপের জন্য।  

📌 **Example: React Controlled Input Field**  

```jsx
import { useState } from "react";
import ReactDOM from 'react-dom/client';

function MyForm() {
  const [name, setName] = useState(""); // State for input field

  return (
    <form>
      <label>Enter your name:
        <input
          type="text" 
          value={name}
          onChange={(e) => setName(e.target.value)} // Updates state
        />
      </label>
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

---

### 🔍 Code Explanation (কোড ব্যাখ্যা)  

✔ **`useState("")`** → `name` নামে state তৈরি করা হয়েছে, যা ইনপুট ফিল্ডের মান সংরক্ষণ করবে।  
✔ **`value={name}`** → ইনপুট ফিল্ডের মান state থেকে নেওয়া হচ্ছে।  
✔ **`onChange={(e) => setName(e.target.value)}`** → ইউজার যখন ইনপুট টাইপ করে, state আপডেট হয়।  

📌 **React Hooks সম্পর্কে আরও জানতে, React Hooks সেকশন দেখো!** 😊

### 🚀 Handling Multiple Input Fields in React (একাধিক ইনপুট ফিল্ড হ্যান্ডলিং)  

React-এ **একাধিক ইনপুট ফিল্ড ম্যানেজ করা যায়** `name` অ্যাট্রিবিউট এবং **state object** ব্যবহার করে।  

---

### 🎯 Key Concepts (মূল বিষয়সমূহ)  

✅ **`useState({})`** → প্রথমে state-কে খালি অবজেক্ট `{}` হিসাবে সেট করা হয়।  
✅ **`name` attribute** → প্রতিটি ইনপুট ফিল্ডের `name` অ্যাট্রিবিউট সেট করতে হয়।  
✅ **`event.target.name` এবং `event.target.value`** → ইউজারের ইনপুট সংগ্রহ করতে ব্যবহৃত হয়।  
✅ **Bracket Notation `[name]: value`** → State আপডেট করতে `[]` ব্র্যাকেট ব্যবহার করা হয়।  

---

### 📌 Example: React Form with Multiple Input Fields  

```jsx
import { useState } from 'react';
import ReactDOM from 'react-dom/client';

function MyForm() {
  const [inputs, setInputs] = useState({}); // Initial empty state

  const handleChange = (event) => {
    const name = event.target.name; // Get input name
    const value = event.target.value; // Get input value
    setInputs(values => ({ ...values, [name]: value })); // Update state dynamically
  };

  const handleSubmit = (event) => {
    event.preventDefault(); // Prevent page refresh
    alert(`Name: ${inputs.username}, Age: ${inputs.age}`); // Show submitted data
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>Enter your name:
        <input 
          type="text" 
          name="username" 
          value={inputs.username || ""} 
          onChange={handleChange}
        />
      </label>
      <br />
      <label>Enter your age:
        <input 
          type="number" 
          name="age" 
          value={inputs.age || ""} 
          onChange={handleChange}
        />
      </label>
      <br />
      <input type="submit" value="Submit" /> {/* Submit Button */}
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

---

### 🔍 Code Explanation (কোড ব্যাখ্যা)  

✔ **`useState({})`** → `inputs` নামে একটি অবজেক্ট state তৈরি করা হয়েছে।  
✔ **`name` attribute** → `username` এবং `age` ইনপুট ফিল্ডের জন্য আলাদা `name` দেওয়া হয়েছে।  
✔ **`onChange={handleChange}`** → প্রতিটি ইনপুটের মান পরিবর্তন হলে `handleChange` ফাংশন কল হয়।  
✔ **`setInputs(values => ({ ...values, [name]: value }))`** → পুরোনো state রেখে নতুন ইনপুট যোগ করা হয়।  
✔ **`onSubmit={handleSubmit}`** → ফর্ম সাবমিট হলে `handleSubmit` ফাংশন কল হয়।  
✔ **`alert("Name: " + inputs.username + ", Age: " + inputs.age)`** → ইউজারের ইনপুট অ্যালার্ট বক্সে দেখাবে।  

---

### 🎯 Summary (সংক্ষেপে)  

✅ **React-এ একাধিক ইনপুট ফিল্ড ম্যানেজ করতে `name` attribute ব্যবহার করতে হয়।**  
✅ **State আপডেটের জন্য `[]` ব্র্যাকেট নোটেশন ব্যবহার করতে হয়।**  
✅ **`onChange` ইভেন্ট ইউজারের ইনপুট আপডেট করতে ব্যবহৃত হয়।**  
✅ **React-এ `onSubmit` ইভেন্ট হ্যান্ডলার ব্যবহার করে ফর্ম সাবমিট করা যায়।**  

📌 **এখন তুমি React-এ একাধিক ইনপুট ফিল্ড সহজেই ম্যানেজ করতে পারবে! 🚀**
