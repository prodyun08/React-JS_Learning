# Modules
- JavaScript modules allow you to break up your code into separate files.

- This makes it easier to maintain the code-base.

- ES Modules rely on the import and export statements.

  # Export

- You can export a function or variable from any file.

- Let us create a file named person.js, and fill it with the things we want to export.

- There are two types of exports: Named and Default.

# Named Exports
You can create named exports two ways. In-line individually, or all at once at the bottom.

Example
In-line individually: `person.js`
```js
export const name = "Jesse"
export const age = 40
```
#### All at once at the bottom:
`person.js`
```js
const name = "Jesse"
const age = 40

export { name, age }
```
# Default Exports
Let us create another file, named message.js, and use it for demonstrating default export.
You can only have one default export in a file.

`message.js`
```js
const message = () => {
  const name = "Jesse";
  const age = 40;
  return name + ' is ' + age + 'years old.';
};

export default message;
```

# Import
- You can import modules into a file in two ways, based on if they are named exports or default exports.
- Named exports must be destructured using curly braces. Default exports do not.
Import named exports from the file person.js:
```js
import { name, age } from `"./person.js";`
```

Import a default export from the file `message.js`:
```js
import message from "./message.js";
```
