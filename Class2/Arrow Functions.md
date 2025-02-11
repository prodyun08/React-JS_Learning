# Arrow function

Arrow function আমাদের বড়ো function গুলোকে ছোট function syntax এ লিখতে সাহায্য করে। 

#### Example: 
```md
# Before Code
students = function() {
  return "All Students";
}

# With Arrow Function:
students = () => {
  return "All Students";
}
```
আপনি শুধুমাত্র এক লাইন এর মধেই পুরো function টি লিখতে পারেন যদি আপনার কাছে একটি statement থাকে এর আপনার statement থেকে কোনো value returns করা হয় আপনি এই function টির জন্য brackets and the return keyword দুটোই delete করতে পারেন। 
#### Example
- Arrow Functions Return Value by Default:
```jsx
students = () => "All Students";
```
আপনি যদি <kbd>students() </kbd> function টি call করেন তাহলে <kbd>All Students</kbd> print হবে। 

আপনার কাছে যদি প্যারামিটার থাকে আপনি প্যারেন্টেসের মধ্যে দিয়ে প্যারামিটার পাস করাতে পারেন। কিন্তু যদি আপনার কাছে একটি মাত্র প্যারামিটার থাকে তাহলে প্যারেন্টেসিসটা স্কিপ করে আপনি লিখতে পারেন। 

### Example 
- Arrow Function With Parameters:
```js
<p id="demo"></p>
<script>
hello = (val) => "Hello " + val;
document.getElementById("demo").innerHTML = hello("World"); // Output: Hello World
</script>
```
- Arrow Function Without Parentheses:
```js
<p id="demo"></p>
<script>
hello = (val) => "Hello " + val;

document.getElementById("demo").innerHTML = hello("World"); // Output: Hello World
```
- Arrow Function With Multiple Parameters:
```js
const multiply = (a, b, c) => a * b * c;
console.log(multiply(2, 3, 4)); // Output: 24
```
