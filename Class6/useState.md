# useState Hooks
### **React useState Hook (React-এর useState হুক)**  

👉 **useState Hook** আমাদের **function component**-এ **state track** করতে সাহায্য করে।  

📌 **State মানে হলো এমন ডাটা বা প্রপার্টি যা অ্যাপ্লিকেশনের মধ্যে ট্র্যাক করা প্রয়োজন।**  

---  

### **useState Import করা (Import useState)**  
useState ব্যবহার করার জন্য, আমাদের প্রথমে এটি **import** করতে হবে।  

#### **উদাহরণ:**  
কম্পোনেন্টের শীর্ষে useState ইম্পোর্ট করুন:  

```jsx
import { useState } from "react";
```
👉 এখানে আমরা **useState**-কে **destructuring** করে ইম্পোর্ট করেছি, কারণ এটি **named export**।  

---  

### **useState ইনিশিয়ালাইজ করা (Initialize useState)**  
আমরা **useState** কল করে **state initialize** করতে পারি।  

📌 **useState দুটি ভ্যালু রিটার্ন করে:**  
1️⃣ **বর্তমান state (current state)**  
2️⃣ **একটি ফাংশন (state updater function), যা state আপডেট করতে ব্যবহৃত হয়।**  

#### **উদাহরণ:**  
```jsx
import { useState } from "react";

function FavoriteColor() {
  const [color, setColor] = useState("");
}
```
👉 এখানে **color** হলো **বর্তমান state**, এবং **setColor** হলো **state আপডেটার ফাংশন**।  

👉 আমরা **state-এর initial value** **useState("")** দিয়ে সেট করেছি।  

---  

### **State পড়া (Read State)**  
আমরা এখন **state-এর মান** কম্পোনেন্টের মধ্যে দেখাতে পারি।  

#### **উদাহরণ:**  
```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";

function FavoriteColor() {
  const [color, setColor] = useState("red");

  return <h1>My favorite color is {color}!</h1>
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<FavoriteColor />);
```
👉 এখানে **{color}** ব্যবহার করে **state-এর মান দেখানো হয়েছে।**  

---  

### **State আপডেট করা (Update State)**  
👉 **state সরাসরি পরিবর্তন করা যাবে না।**  
❌ **color = "red";** ❌ **এটি অনুমোদিত নয়।**  

👉 **আমাদের state আপডেট করার জন্য state updater function ব্যবহার করতে হবে।**  

#### **উদাহরণ:**  
```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";

function FavoriteColor() {
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My favorite color is {color}!</h1>
      <button type="button" onClick={() => setColor("blue")}>Blue</button>
    </>
  )
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<FavoriteColor />);
```
👉 এখানে **setColor("blue")** ব্যবহার করে **state পরিবর্তন করা হয়েছে।**  

---  

### **State-এ কী কী সংরক্ষণ করা যায়? (What Can State Hold)**  
👉 useState **string, number, boolean, array, object** ইত্যাদি সংরক্ষণ করতে পারে।  

#### **একাধিক state ব্যবহার করা (Multiple State Hooks)**  
```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";

function Car() {
  const [brand, setBrand] = useState("Ford");
  const [model, setModel] = useState("Mustang");
  const [year, setYear] = useState("1964");
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My {brand}</h1>
      <p>It is a {color} {model} from {year}.</p>
    </>
  )
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
👉 এখানে **একাধিক state** ব্যবহার করা হয়েছে **প্রত্যেকটি আলাদা মান track** করতে।  

---  

### **একটি Object হিসেবে state সংরক্ষণ করা (State as an Object)**  
আমরা **একটি object** হিসেবে **state সংরক্ষণ** করতে পারি।  

#### **উদাহরণ:**  
```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";

function Car() {
  const [car, setCar] = useState({
    brand: "Ford",
    model: "Mustang",
    year: "1964",
    color: "red"
  });

  return (
    <>
      <h1>My {car.brand}</h1>
      <p>It is a {car.color} {car.model} from {car.year}.</p>
    </>
  )
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
👉 এখানে **একটি object** হিসেবে **state track করা হয়েছে।**  

---  

### **Object এবং Array Update করা (Updating Objects and Arrays in State)**  
👉 **state পরিবর্তন করলে পুরানো state মুছে যায়**।  
👉 **state-এর নির্দিষ্ট অংশ আপডেট করতে JavaScript spread operator ব্যবহার করা হয়।**  

#### **শুধুমাত্র color আপডেট করা:**  
```jsx
import { useState } from "react";
import ReactDOM from "react-dom/client";

function Car() {
  const [car, setCar] = useState({
    brand: "Ford",
    model: "Mustang",
    year: "1964",
    color: "red"
  });

  const updateColor = () => {
    setCar(previousState => {
      return { ...previousState, color: "blue" }
    });
  }

  return (
    <>
      <h1>My {car.brand}</h1>
      <p>It is a {car.color} {car.model} from {car.year}.</p>
      <button type="button" onClick={updateColor}>Blue</button>
    </>
  )
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
👉 এখানে **JavaScript spread operator (...previousState)** ব্যবহার করা হয়েছে, যাতে **পুরানো state হারিয়ে না যায় এবং শুধুমাত্র color আপডেট হয়।**  

---

✅ **সংক্ষেপে:**  
- **useState Hook** React function components-এ **state পরিচালনা করতে ব্যবহৃত হয়।**  
- **useState দুটি ভ্যালু রিটার্ন করে:** বর্তমান **state** এবং একটি **state আপডেটার ফাংশন**।  
- **state সরাসরি পরিবর্তন করা যায় না**, **state updater function ব্যবহার করতে হয়।**  
- **একাধিক state ব্যবহারের বদলে object হিসেবে state সংরক্ষণ করা সুবিধাজনক হতে পারে।**  
- **state আপডেট করার সময় JavaScript spread operator ব্যবহার করে পুরানো state সংরক্ষণ করতে হয়।**