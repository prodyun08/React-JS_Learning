# Ternary Operator

- The ternary operator is a simplified conditional operator like if / else.
- Syntax: condition ? <expression if true> : <expression if false>
- Here is an example using if / else:

 ```js
  <h1 id="demo"></h1>
<script>
function renderApp() {
  document.getElementById("demo").innerHTML = "Welcome!";
}
function renderLogin() {
  document.getElementById("demo").innerHTML = "Please log in";
}
let authenticated = true;
// let authenticated = false;
authenticated ? renderApp() : renderLogin();
</script>
<p>Try changing the "authenticated" variable to false, and run the code to see what happens.</p>

```
- The `<h1>` tag with `id="demo"` is initially empty.
- Two JavaScript functions are defined:
- `renderApp()`: Sets the content of `<h1>` to "Welcome!".
- `renderLogin()`: Sets the content of `<h1>` to "Please log in".
- The variable `authenticated` is set to `true`.
- A ternary operator `(condition ? expr1 : expr2)` is used:
- If `authenticated === true`, `renderApp()` is executed, setting "Welcome!" in `<h1>`.
- If `authenticated === false`, `renderLogin()` is executed, setting "Please log in" in `<h1>`.
- If you manually change authenticated to `false`, "Please log in" will be displayed instead.

### Test it
- Set `authenticated = false;` in the script and reload the page.
- The text will change from `"Welcome!"` to `"Please log in"`.
