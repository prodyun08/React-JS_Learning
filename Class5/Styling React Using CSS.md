# Styling React Using CSS

# 🎨 **Styling React Components Using CSS**
React-এ CSS ব্যবহার করার **তিনটি জনপ্রিয় পদ্ধতি** হলো:  
✅ **Inline Styling**  
✅ **CSS Stylesheets**  
✅ **CSS Modules**  

---

## 🔵 **1. Inline Styling**
**`style` অ্যাট্রিবিউটের মধ্যে JavaScript অবজেক্ট দিয়ে স্টাইল দেওয়া হয়।**  
👉 **Syntax:** `{ { property: "value" } }`  

### **📌 Example: Inline CSS**
```jsx
const Header = () => {
  return (
    <>
      <h1 style={{ color: "red" }}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
}
```
📌 **`color` প্রপার্টি সরাসরি `h1` ট্যাগে দেওয়া হয়েছে।**

---

## 🟢 **2. CamelCased Property Names**
👉 **JSX-এ hyphenated CSS properties (যেমন: `background-color`) ক্যামেলকেস (`backgroundColor`) করতে হয়।**  

### **📌 Example:**
```jsx
const Header = () => {
  return (
    <>
      <h1 style={{ backgroundColor: "lightblue" }}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
}
```
📌 **`background-color` → `backgroundColor` ক্যামেলকেস করতে হবে।**  

---

## 🟠 **3. JavaScript Object for Styling**
👉 **স্টাইল সংরক্ষণের জন্য JavaScript অবজেক্ট ব্যবহার করা যায়।**  

### **📌 Example: Using a Style Object**
```jsx
const Header = () => {
  const myStyle = {
    color: "white",
    backgroundColor: "DodgerBlue",
    padding: "10px",
    fontFamily: "Sans-Serif"
  };

  return (
    <>
      <h1 style={myStyle}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
}
```
📌 **`myStyle` অবজেক্টের মাধ্যমে স্টাইল আলাদা রাখা হয়েছে।**

---

## 🔵 **4. CSS Stylesheets (External CSS)**
👉 **CSS আলাদা `.css` ফাইলে লিখে তারপর ইমপোর্ট করা যায়।**  

### **📌 Example: `App.css`**
```css
/* App.css */
body {
  background-color: #282c34;
  color: white;
  padding: 40px;
  font-family: Sans-Serif;
  text-align: center;
}
```
📌 **এই CSS `body` ট্যাগে প্রভাব ফেলবে।**  

### **📌 Example: Importing the Stylesheet**
```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import "./App.css"; // Import the CSS file

const Header = () => {
  return (
    <>
      <h1>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Header />);
```
📌 **`import './App.css'` দিয়ে স্টাইল অ্যাপ্লাই করা হয়েছে।**  

---

## 🟢 **5. CSS Modules (Scoped CSS)**
👉 **CSS Modules ব্যবহার করলে শুধু সেই নির্দিষ্ট কম্পোনেন্টেই CSS প্রভাব ফেলে।**  

### **📌 Example: `my-style.module.css`**
```css
/* my-style.module.css */
.bigblue {
  color: DodgerBlue;
  padding: 40px;
  font-family: Sans-Serif;
  text-align: center;
}
```
📌 **এই CSS শুধুমাত্র যেই কম্পোনেন্টে ইমপোর্ট করা হবে, সেইখানেই প্রযোজ্য হবে।**  

### **📌 Example: Using the Module in `Car.js`**
```jsx
import styles from "./my-style.module.css"; 

const Car = () => {
  return <h1 className={styles.bigblue}>Hello Car!</h1>;
}

export default Car;
```
📌 **`className={styles.bigblue}` দিয়ে মডিউল CSS অ্যাপ্লাই করা হয়েছে।**  

### **📌 Importing `Car` in `index.js`**
```jsx
import ReactDOM from "react-dom/client";
import Car from "./Car.js";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Car />);
```
📌 **এটি শুধুমাত্র `Car` কম্পোনেন্টের CSS লোড করবে।**

---

## 🎯 **Summary**
| Method  | Description | Best Use Case |
|---------|------------|--------------|
| **Inline Styling** | `style={{ color: "red" }}` | Quick, simple styles |
| **CSS Stylesheets** | `import "./App.css"` | Global styling |
| **CSS Modules** | `import styles from "./style.module.css"` | Component-specific styling |

---

## 🚀 **Conclusion**
✅ **Inline CSS**: দ্রুত, কিন্তু বেশি ব্যবহারের জন্য ভালো নয়।  
✅ **CSS Stylesheets**: পুরো অ্যাপে একই স্টাইল ব্যবহারের জন্য পারফেক্ট।  
✅ **CSS Modules**: **নাম ক্ল্যাশ এড়াতে** ও **কম্পোনেন্ট-স্পেসিফিক স্টাইলিং** এর জন্য সেরা।  

🔥 **তুমি এখন React-এ CSS স্টাইলিং করতে পুরোপুরি প্রস্তুত!** 🚀
