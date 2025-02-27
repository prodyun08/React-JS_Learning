# React JSX

### What is JSX?
JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React.

### Coding JSX
JSX allows us to write HTML elements in JavaScript and place them in the DOM without any `createElement()`  and/or `appendChild()` methods.

JSX converts HTML tags into react elements.

- **You are not required to use JSX, but JSX makes it easier to write React applications.**

Here are two examples. The first uses JSX and the second does not:

#### Example 
*JSX:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = <h1>I Love JSX!</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

*Without JSX:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = React.createElement('h1', {}, 'I do not use JSX!');

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```


### Expressions in JSX
With JSX you can write expressions inside curly braces { }.

The expression can be a React variable, or property, or any other valid JavaScript expression. JSX will execute the expression and return the result:
Execute the expression `5 + 5`:
```jsx
const myElement = <h1>React is {5 + 5} times better with JSX</h1>;
```

### Inserting a Large Block of HTML
To write HTML on multiple lines, put the HTML inside parentheses:

- Create a list with three list items:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
);

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

## One Top Level Element
The HTML code must be wrapped in ONE top level element.

So if you like to write two paragraphs, you must put them inside a parent element, like a div element.
- Wrap two paragraphs inside one DIV element:

```jsx
import React from 'react';
import ReactDOM from 'react-do/client';

const myElement = (
  <div>
    <h1>I am a Header.</h1>
    <h1>I am a Header too.</h1>
  </div>
);

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
**JSX will throw an error if the HTML is not correct, or if the HTML misses a parent element.**
Alternatively, you can use a "fragment" to wrap multiple lines. This will prevent unnecessarily adding extra nodes to the DOM.

A fragment looks like an empty HTML tag: `<></>`.
- Wrap two paragraphs inside a fragment:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = (
    <>
      <p>I am a paragraph.</p>
      <p>I am a paragraph too.</p>
    </>
  );

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
### Elements Must be Closed
JSX follows XML rules, and therefore HTML elements must be properly closed.

- Close empty elements with />
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = <input type="text" />;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
*JSX will throw an error if the HTML is not properly closed.*
## Attribute class = className
The `class` attribute is a much used attribute in HTML, but since JSX is rendered as JavaScript, and the class keyword is a reserved word in JavaScript, you are not allowed to use it in JSX.

*Use attribute className instead.*
JSX solved this by using `className` instead. When JSX is rendered, it translates `className` attributes into `class` attributes.
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const myElement = <h1 className="myclass">Hello World</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

### Conditions - if statements
React supports if statements, but not inside JSX.

To be able to use conditional statements in JSX, you should put the if statements outside of the JSX, or you could use a ternary expression instead:

Option 1:
Write if statements outside of the JSX code:
*Write "Hello" if x is less than 10, otherwise "Goodbye":* 
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const x = 5;
let text = "Goodbye";
if (x < 10) {
  text = "Hello";
}

const myElement = <h1>{text}</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

Option 2:
Use ternary expressions instead:

*Write "Hello" if x is less than 10, otherwise "Goodbye":*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

const x = 5;

const myElement = <h1>{(x) < 10 ? "Hello" : "Goodbye"}</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
*Note that in order to embed a JavaScript expression inside JSX, the JavaScript must be wrapped with curly braces, `{}`.*


# Writing markup with JSX 
The markup syntax you’ve seen above is called *JSX*. It is optional, but most React projects use JSX for its convenience. All of the tools we recommend for local development support JSX out of the box.

JSX is stricter than HTML. You have to close tags like `<br />`. Your component also can’t return multiple JSX tags. You have to wrap them into a shared parent, like a `<div>...</div>` or an empty `<>...</>` wrapper:

```diff
function AboutPage() {
  return (
+    <>
       <h1>About</h1>
       <p>Hello there.<br />How do you do?</p>
+    </>
  );
}
```
# Displaying data 
JSX lets you put markup into JavaScript. Curly braces let you “escape back” into JavaScript so that you can embed some variable from your code and display it to the user. For example, this will display `user.name`:
```js
return (
  <h1>
    {user.name} 
  </h1>
);
```

You can also “escape into JavaScript” from JSX attributes, but you have to use curly braces instead of quotes. For example, `className="avatar"` passes the "avatar" string as the CSS class, but `src={user.imageUrl}` reads the JavaScript `user.imageUrl` variable value, and then passes that value as the `src` attribute:

```js
return (
  <img
    className="avatar"
    src={user.imageUrl}
  />
);
```



## More Imformation Read [React Official Docs](https://react.dev/learn) 👾🐱‍🏍
