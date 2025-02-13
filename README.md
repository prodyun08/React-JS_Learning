# React-JS_Learning

## What is React JS?

**React JS** হল একটি **Frontend JavaScript Framework** যা **website** এর **UI design** তৈরি করতে ব্যবহার করা হয়। এটি **Facebook** কোম্পানি দ্বারা তৈরি।

### Features of React JS
- **Component-Based Architecture** – UI কে ছোট ছোট পুনঃব্যবহারযোগ্য কম্পোনেন্টে ভাগ করে।
- **Virtual DOM** – দ্রুত রেন্ডারিং এবং পারফরম্যান্স উন্নত করে।
- **JSX Syntax** – JavaScript এর ভিতরে HTML লেখার সুবিধা দেয়।
- **Unidirectional Data Flow** – একমুখী ডাটা প্রবাহ, যা অ্যাপ্লিকেশন ম্যানেজ করা সহজ করে।
- **React Hooks** – Functional components এর জন্য built-in hooks ব্যবহার করা যায়।

### How Does React Work?
React creates a **VIRTUAL DOM** in memory.

Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.

React only changes what needs to be changed!

React finds out what changes have been made, and changes only what needs to be changed.

আপনি এই টিউটোরিয়ালের বাকি অংশে শিখবেন কিভাবে React এটি করে।
### Installation
React JS ইন্সটল করতে **Node.js** ইন্সটল থাকতে হবে।

```sh
npx create-react-app my-app
cd my-app
npm start
```

### Example Code
```jsx
import React from 'react';

function App() {
  return (
    <div>
      <h1>Welcome to React JS</h1>
    </div>
  );
}

export default App;
```

### Why Use React JS?
✅ সহজে শিখতে পারা যায়।
✅ High Performance (Virtual DOM ব্যবহার করে দ্রুত রেন্ডারিং)।
✅ Component-Based Architecture, যা পুনঃব্যবহারযোগ্য করে।
✅ React Native এর মাধ্যমে **mobile app development** করা যায়।

### Conclusion
React JS হল **একটি জনপ্রিয় JavaScript লাইব্রেরি** যা **Frontend Development** কে সহজ ও দ্রুততর করে। এটি বড় স্কেলের **Web Apps** তৈরি করতে খুবই কার্যকর।

### Install Tailwind CSS
```js
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### Configure your template paths 

```md
# tailwind.config.js

content:[
  "./index.html",
  "./src/**/*.{js,ts,jsx,tsx}",
],
```

### Add the Tailwind directives to your CSS
Add the '@tailwind' directives for each of Tailwind's layers to your './src/index.css' file.
```js
@tailwind base;
@tailwind components;
@tailwind utilities;
```
### Start your build process
run build process `npm run dev`
