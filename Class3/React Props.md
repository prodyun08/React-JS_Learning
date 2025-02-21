# React Props
- Props হল React components পাঠানো arguments.
- Props HTML attributes মাধ্যমে components passed করা হয়।

*props stands for properties.*

---
👉 **Props হল React Component-এ data পাঠানোর উপায়।**  
👉 **JavaScript-এর function arguments এবং HTML attributes-এর মতো কাজ করে।**  
👉 **Parent Component থেকে Child Component-এ Props পাঠানো হয়।**  


### **🛠 Example: How to Use Props**
```jsx
function Car(props) {
  return <h2>I am a {props.brand}!</h2>;
}

function Garage() {
  return (
    <div>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
    </div>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<Garage />);
```

✅ **Garage Component → `Car` Component-এ `brand="Ford"` Props পাঠাচ্ছে।**  
✅ **Car Component `props.brand` ব্যবহার করে "I am a Ford!" print করছে।**  

### **🔹 Multiple Props ব্যবহার করা**
```jsx
function Car(props) {
  return <h2>I have a {props.brand}, Model: {props.model}!</h2>;
}

function Garage() {
  return (
    <div>
      <Car brand="Toyota" model="Corolla" />
    </div>
  );
}
```
✅ **এখানে `props.brand → "Toyota"` এবং `props.model → "Corolla"` পাঠানো হয়েছে।**  

---

### **🔹 Object আকারে Props পাঠানো**
```jsx
function Car(props) {
  return <h2>I am a {props.carInfo.brand}, Model: {props.carInfo.model}!</h2>;
}

function Garage() {
  const car = { brand: "Tesla", model: "Model X" };
  return (
    <div>
      <Car carInfo={car} />
    </div>
  );
}
```
✅ **Props `carInfo` নামে object আকারে পাঠানো হয়েছে এবং `Car` Component-এ ব্যবহার করা হয়েছে।**  


## Pass Data
