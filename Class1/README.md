# Getting Started

React ব্যবহার করতে হলে আপনার system এ [Nodejs](https://nodejs.org/en) installed থাকা চাই। 

### চলুন দেখে নেওয়া যাক কিভাবে React Js কে আপনি ব্যবহার করবেন

আপনি direct HTML এর মধ্যেও React code লিখতে পারবেন। কিন্তু আপনি React কে run করতে গেলে আপনার system এ অবশ্যই npm & Nodejs installed থাকতে হবে। 

কিভাবে দেখবেন আপনার system a npm & nodejs installed আছে?
- <kbd><img src="https://github.com/desihacker08/Activate-Windows-8-8.1-10-and-11-Pro-for-Free/blob/Coad/icon/icons8-windows-10-100.png" width="20"></kbd> + X  click করলে একটা popup menu খুলবে। এখানে আপনি Windows Powershell এ click করবেন। আপনি nodejs & npm installed আছে দেখার জন্য <kbd>npm --version</kbd> লিখে Enter করবেন। 11.1.0 এরকম লেখা আসলে বুঝবেন আপনার system a npm install আছে। একই process এ <kbd>node --version</kbd> দেখবেন। 

### React Directly in HTML
খুব দ্রুত পদ্ধতিতে যদি আপনি React শিখতে চান তাহলে আপনি HTML এর মধেই React CDN এর মাধ্যমে শিখতে পারেন। 
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Hello World</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <!-- Don't use this in production: -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
    
      function MyApp() {
        return <h1>Hello, world!</h1>;
      }

      const container = document.getElementById('root');
      const root = ReactDOM.createRoot(container);
      root.render(<MyApp />);

    </script>
    <!--
      Note: this page is a great way to try React but it's not suitable for production.
      It slowly compiles JSX with Babel in the browser and uses a large development build of React.

      Read this page for starting a new React project with JSX:
      https://react.dev/learn/start-a-new-react-project

      Read this page for adding React with JSX to an existing project:
      https://react.dev/learn/add-react-to-an-existing-project
    -->
  </body>
</html>
```
এই code এর মধ্যে 3টে script line আছে এদের কাজ 
### first line
```js
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
``` 
এই script দিয়ে HTML এর সাথে CDN used করে react js কে link করা হচ্ছে। 

### second line 
```js
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
``` 
react-dom এটির কাজ হল code টিকে browser/web এ run করা। 

### third line 
```js
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

এই code এ মাধ্যমে বলা হচ্ছে The script is used in HTML code to enable writing modern JavaScript (JSX, ES6+) directly in the browser without the need for a build tool like Webpack or Babel CLI. 

শুধুমাত্র testing purpose এর ক্ষেত্রেই এই পধতি ব্যাবহার করা যেতে পারে। কিন্তু যদি আপনি react js এর production ব্যবহার করতে চান তাহলে আপনাকে পুরো React এর environment setup করতে হবে। 


# Setting up a React Environment

যদি আপনার system এ [npx](https://www.npmjs.com/package/npx) & [Nodejs](https://nodejs.org/en) installed থাকে তাহলে আপনি ```create-react-app``` এর মাধ্যমে react application create করতে পারেন। 

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
application run করার জন্য 
```md
npm start
```
একটি popup দিয়ে default browser open হবে & ```localhost:3000``` location আপনার applicaiton টি run হবে। 

#### The most Important notice is if you Instead, use a build tool like Vite, Webpack, or Parcel to compile the code before deployment.
Installation process :
[Vite](https://vite.dev/guide/#scaffolding-your-first-vite-project)
[Webpack](https://webpack.js.org/guides/installation/#local-installation)
[Parcel](https://parceljs.org/recipes/react/#getting-started)


very important notice for react 18 upgrade just click [here](https://www.w3schools.com/REACT/react_upgrade.asp)
