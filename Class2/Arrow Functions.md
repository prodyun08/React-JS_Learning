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
