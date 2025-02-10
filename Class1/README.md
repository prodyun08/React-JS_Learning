# Getting Started

React ব্যবহার করতে হলে আপনার system এ [Nodejs](https://nodejs.org/en) installed থাকা চাই। 

### চলুন দেখে নেওয়া যাক কিভাবে React Js কে আপনি ব্যবহার করবেন

আপনি direct HTML এর মধ্যেও React code লিখতে পারবেন। কিন্তু আপনি React কে run করতে গেলে আপনার system এ অবশ্যই npm & Nodejs installed থাকতে হবে। 

কিভাবে দেখবেন আপনার system a npm & nodejs installed আছে?
- <kbd><img src="https://github.com/desihacker08/Activate-Windows-8-8.1-10-and-11-Pro-for-Free/blob/Coad/icon/icons8-windows-10-100.png" width="20"></kbd> + X  click করলে একটা popup menu খুলবে। এখানে আপনি Windows Powershell এ click করবেন। আপনি nodejs & npm installed আছে দেখার জন্য <kbd>npm --version</kbd> লিখে Enter করবেন। 11.1.0 এরকম লেখা আসলে বুঝবেন আপনার system a npm install আছে। একই process এ <kbd>nodejs --version</kbd> দেখবেন। 

### React Directly in HTML
খুব দ্রুত পদ্ধতিতে যদি আপনি React শিখতে চান তাহলে আপনি HTML এর মধেই React CDN এর মাধ্যমে শিখতে পারেন। 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Directly React in HTML Example</title>
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
এই code এর মধ্যে 3টে script line আছে এদের কাজ 
### first line
```<script src="https://unpkg.com/react@17/umd/react.development.js"></script>``` 
এই script দিয়ে HTML এর সাথে CDN used করে react js কে link করা হচ্ছে। 

### second line 
```<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>``` 
react-dom এটির কাজ হল code টিকে browser/web এ run করা। 

### third line 
```<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>```
এই code এ মাধ্যমে বলা হচ্ছে The script is used in HTML code to enable writing modern JavaScript (JSX, ES6+) directly in the browser without the need for a build tool like Webpack or Babel CLI. 

শুধুমাত্র testing purpose এর ক্ষেত্রেই এই পধতি ব্যাবহার করা যেতে পারে। কিন্তু যদি আপনি react js এর production ব্যবহার করতে চান তাহলে আপনাকে পুরো React এর environment setup করতে হবে। 


# Setting up a React Environment

যদি আপনার system এ npx & [Nodejs](https://nodejs.org/en) installed থাকে তাহলে আপনি ```create-react-app``` এর মাধ্যমে react application create করতে পারেন। 

```shell
npx create-react-app my-react-app
```
আপনি দেখতে পাবেন আপনার location এ my-react-app নামে একটি folder create হবে। 
```md
# Project Structure

- 📂 my-react-app/
  |- 📂 node_modules/ 
  |- 📂 src/
  |  |- 📄 App.css          # Styles for the App component
  |  |- 📄 App.js           # Main App component
  |  |- 📄 App.test.js      # Test file for the App component
  |  |- 📄 index.css        # Global CSS styles
  |  |- 📄 index.js         # Entry point of the React app
  |  |- 📄 logo.svg         # Default React logo
  |  |- 📄 reportWebVitals.js # Performance monitoring
  |  |- 📄 setupTests.js    # Test setup
  |- 📂 public/
  |  |- 📄 index.html
  |  |- 📄 favicon.ico
  |  |- 📄 manifest.json
  |  |- 📄 package.json
  |- 📄 .gitignore           # Files to ignore in Git
  |- 📄 package.json         # Project dependencies and scripts
  |- 📄 package-lock.json    # Dependency lock file
```
দেখবেন আপনার ওই file location a এই রকম related file show করবে। জানবেন আপনার file installation procress complete হয়েছে। next আপনি
```md
cd my-react-app
```
করে আপনার folder এর মধ্যে যাবেন আর run করবেন।

```md
npm install
```
