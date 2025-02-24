# React Router
### 🚀 React Router (v6) ব্যবহার করে Page Routing  

React-এ `Create React App` ডিফল্টভাবে **page routing** সাপোর্ট করে না, তাই **React Router** ব্যবহার করা হয়।  

---

## 📌 Step 1: Install React Router  

টার্মিনালে নিচের কমান্ডটি রান করো:  

```bash
npm i -D react-router-dom
```

**Note:** যদি তুমি `v5` থেকে `v6`-এ আপগ্রেড করো, তাহলে `@latest` যুক্ত করে ইনস্টল করো:  

```bash
npm i -D react-router-dom@latest
```

---

## 📂 Step 2: Folder Structure  

```
src/
 ├── pages/
 │   ├── Layout.js
 │   ├── Home.js
 │   ├── Blogs.js
 │   ├── Contact.js
 │   ├── NoPage.js
 ├── index.js
 ├── App.js
```

---

## 📜 Step 3: Setup Routes in `index.js`  

```jsx
import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} /> 
          <Route path="blogs" element={<Blogs />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

## 🏠 Step 4: Create Individual Page Components  

### ✅ `Layout.js` (Navigation & Route Outlet)  

```jsx
import { Outlet, Link } from "react-router-dom";

const Layout = () => {
  return (
    <>
      <nav>
        <ul>
          <li><Link to="/">Home</Link></li>
          <li><Link to="/blogs">Blogs</Link></li>
          <li><Link to="/contact">Contact</Link></li>
        </ul>
      </nav>

      <Outlet /> {/* This renders the current page */}
    </>
  );
};

export default Layout;
```

---

### ✅ `Home.js`  

```jsx
const Home = () => {
  return <h1>🏠 Welcome to Home Page</h1>;
};

export default Home;
```

---

### ✅ `Blogs.js`  

```jsx
const Blogs = () => {
  return <h1>📝 Blog Articles</h1>;
};

export default Blogs;
```

---

### ✅ `Contact.js`  

```jsx
const Contact = () => {
  return <h1>📞 Contact Me</h1>;
};

export default Contact;
```

---

### ✅ `NoPage.js` (404 Page)  

```jsx
const NoPage = () => {
  return <h1>❌ 404 - Page Not Found</h1>;
};

export default NoPage;
```

---

## 🎯 Explanation  

✅ **`<BrowserRouter>`** → সব Route **Wrap** করতে হবে।  
✅ **`<Routes>`** → একাধিক Route গঠনের জন্য।  
✅ **`<Route>`** → প্রতিটি আলাদা পেজের জন্য আলাদা Route তৈরি করা হয়।  
✅ **`<Outlet>`** → **`Layout.js`**-এ `Outlet` ব্যবহার করা হয়, যাতে বর্তমান **child route** রেন্ডার হয়।  
✅ **`<Link>`** → HTML `<a>` ট্যাগের পরিবর্তে **React Router-এর** `<Link>` ব্যবহার করা হয়।  

---

## 🛠 Now, Your React App Supports Multiple Pages! 🚀  

এখন যদি তুমি `/blogs` বা `/contact` URL-এ যাও, তাহলে পেজ পরিবর্তন হবে, **refresh ছাড়াই!** 😍
