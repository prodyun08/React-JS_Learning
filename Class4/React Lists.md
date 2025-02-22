# React Lists
In React, you will render lists with some type of loop.

The JavaScript map() array method is generally the preferred method.
*If you need a refresher on the map() method, check out the ES6 section.*
#### Example:
*Let's render all of the cars from our garage:*
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';

function Car(props) {
  return <li>I am a { props.brand }</li>;
}

function Garage() {
  const cars = ['Ford', 'BMW', 'Audi'];
  return (
    <>
	    <h1>Who lives in my garage?</h1>
	    <ul>
        {cars.map((car) => <Car brand={car} />)}
      </ul>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);

/*
If you run this example in your create-react-app,
you will receive a warning that there is no "key" provided for the list items.
*/
```

When you run this code in your `create-react-app`, it will work but you will receive a warning that there is no "[key](#key)" provided for the list items.


## Key
Keys allow React to keep track of elements. This way, if an item is updated or removed, only that item will be re-rendered instead of the entire list.


