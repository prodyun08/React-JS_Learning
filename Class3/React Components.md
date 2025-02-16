# React Components

### Creating and nesting components 

React apps are made out of components. A component is a piece of the UI (user interface) that has its own logic and appearance. A component can be as small as a button, or as large as an entire page.

- React components are JavaScript functions that return markup:

```js
function MyButton() {
  return (
    <button>I'm a button</button>
  );
}
```

Now that you’ve declared `MyButton`, you can nest it into another component:

```js
export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}
```
Notice that `<MyButton />` starts with a capital letter. That’s how you know it’s a React component. React component names must always start with a capital letter, while HTML tags must be lowercase.

Have a look at the result:

```js
function MyButton() {
  return (
    <button>
      I'm a button
    </button>
  );
}

export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />
    </div>
  );
}
```
The `export` `default` keywords specify the main component in the file. If you’re not familiar with some piece of JavaScript syntax, [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) and [javascript.info](https://javascript.info/import-export) have great references.



### Create Your First Component
When creating a React component, the component's name MUST start with an upper case letter.

#### Class Component
A class component must include the `extends React.Component` statement. This statement creates an inheritance to React.Component, and gives your component access to React.Component's functions.

The component also requires a `render()` method, this method returns HTML.

*Create a Class component called Car*
```jsx
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```


#### Function Component
Here is the same example as above, but created using a Function component instead.

A Function component also returns HTML, and behaves much the same way as a Class component, but Function components can be written using much less code, are easier to understand, and will be preferred in this tutorial.

*Create a Function component called Car*

```jsx
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```
#### Rendering a Component
Now your React application has a component called Car, which returns an `<h2>` element.

To use this component in your application, use similar syntax as normal HTML: `<Car />`
*Display the Car component in the "root" element:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car() {
  return <h2>Hi, I am a Car!</h2>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

## [Props](https://react.dev/learn/passing-props-to-a-component)
Components can be passed as props, which stands for properties.

Props are like function arguments, and you send them into the component as attributes.

You will learn more about props in the next chapter.
*Use an attribute to pass a color to the Car component, and use it in the render() function:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <h2>I am a {props.color} Car!</h2>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car color="red"/>);
```

## Components in Components
- We can refer to components inside other components:

*Use the Car component inside the Garage component:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car() {
  return <h2>I am a Car!</h2>;
}

function Garage() {
  return (
    <>
	    <h1>Who lives in my Garage?</h1>
	    <Car />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

## Components in Files
React is all about re-using code, and it is recommended to split your components into separate files.

To do that, create a new file with a .js file extension and put the code inside it:
**Note that the filename must start with an uppercase character.**
*This is the new file, we named it "Car.js":*
```jsx
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}

export default Car;
```
To be able to use the Car component, you have to import the file in your application.

*Now we import the "Car.js" file in the application, and we can use the Car component as if it was created here.*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
