# Classes
ES6 introduced classes.

A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.

- Step 1: Define a Class (```Building```)

```js
class Building {
  constructor(name) {
    this.Structure = name;
  }
}
```
✅ ```class Building {}``` → এটি Car নামে একটি ক্লাস তৈরি করছে।
✅ ```constructor(name) {}``` →

Constructor হলো একটি বিশেষ ফাংশন যা object তৈরি করার সময় স্বয়ংক্রিয়ভাবে চলে।
এটি name প্যারামিটার গ্রহণ করে এবং সেটাকে brand প্রোপার্টির মধ্যে সংরক্ষণ করে।
✅ ```this.Structure = name;``` →
this এখানে নতুন তৈরি হওয়া object কে নির্দেশ করে।
name প্যারামিটারটি Structure প্রোপার্টির মধ্যে সংরক্ষণ করা হয়।

- Step 2: Create an Object (```buildStructure```)
```js
const buildStructure = new Building("Taj Mahal");
```
✅ new Building("Taj Mahal") → এটি Car ক্লাস থেকে একটি নতুন অবজেক্ট তৈরি করে।
✅ Constructor (constructor(name)) স্বয়ংক্রিয়ভাবে চলে, ফলে নিচের কোডটি কার্যকর হয়:

- Step 3: Check the Output
```js
class Building {
  constructor(name) {
    this.Structure = name;
  }
}
const buildStructure = new Building("Taj Mahal");
document.write(buildStructure.Structure);
```
চলুন নিজে থেকে react js এর মধ্যে method বানানোর চেষ্টা করি। 
```js
class Students{
    constructor(name,roll,class)                   //constructor(props)
      /*{
        this.name = name;
        this.roll = roll;
        this.class = class;        
      }*/
      getName()
      {
          return this.name;
        }
      getRoll()
      {
          return this.roll;
        }
      getClass()
      {
          return this.class;
        }
  }
const studentList = new Student("Ram",5,"Xi");
// document.write(studentList.name);              --- document.write(object.props)
document.write(studentList.getName());

-------------------------------------------------------------------
Output: Ram
```


