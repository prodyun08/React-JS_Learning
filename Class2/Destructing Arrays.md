# Destructing Arrays

In this here i will show 2 different way to assigning array items to a variable (old way / New way)
- old way
```js
const num = ['10', '20', '30'];

// old way
const a = num[0];
const b = num[1];
const c = num[2];
```
- new way
```js
const num = ['10', '20', '30'];
const [a, b, c] = num;
```

যদি কোনো ক্ষেত্রে a & b value আমার দরকার নেই সুধুমাত্র c এর value দরকার আছে এই ক্ষেত্রে আমি এই code run করতে পারি - 
```js
const num = ['10','20','30'];
const [,,c] = num; // Output : 30
```
just comma use করে আপনি `a,b` থেকে leave out করতে পারেন। 
