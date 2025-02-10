# Getting Started

React ব্যবহার করতে হলে আপনার system এ [Nodejs](https://nodejs.org/en) installed থাকা চাই। 

### চলুন দেখে নেওয়া যাক কিভাবে React Js কে আপনি ব্যবহার করবেন

আপনি direct HTML এর মধ্যেও React code লিখতে পারবেন। কিন্তু আপনি React কে run করতে গেলে আপনার system এ অবশ্যই npm & Nodejs installed থাকতে হবে। 

কিভাবে দেখবেন আপনার system a npm & nodejs installed আছে?
- <kbd><img src="https://github.com/desihacker08/Activate-Windows-8-8.1-10-and-11-Pro-for-Free/blob/Coad/icon/icons8-windows-10-100.png" width="20"></kbd> + X  click করলে একটা popup menu খুলবে। এখানে আপনি Windows Powershell এ click করবেন। আপনি nodejs & npm installed আছে দেখার জন্য <kbd>npm --version</kbd> লিখে Enter করবেন। 11.1.0 এরকম লেখা আসলে বুঝবেন আপনার system a npm install আছে। একই process এ <kbd>nodejs --version</kbd> দেখবেন। 

### React Directly in HTML
খুব দ্রুত পদ্ধতিতে যদি আপনি React শিখতে চান তাহলে আপনি HTML এর মধেই React CDN এর মাধ্যমে শিখতে পারেন। 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Babel Example</title>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
    <script type="text/babel">
        function App() {
            return <h1>Hello, JSX with Babel!</h1>;
        }
        ReactDOM.render(<App />, document.getElementById('root'));
    </script>
</body>
</html>
```
