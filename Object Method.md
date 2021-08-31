# seal(), freeze()
---

1. **Object.seal()**

**Syntex**

```javascript
Object.seal(ObjectName)
```

seal মানে কোন কিছুকে তালা বন্দি করা , যেমন আমরা মাঝে মাঝে দেখি তালাকে আলকাতরা দিয়ে সীল করা হয় যেন কেউ তালাটি না খুলে। এখন ধরুন, আমি সেই সীলগালা রুমের মধ্যে আছি। যেহেতু আমি সীলগালা রুমে বন্দি তাই আমি বাহিরের কোন জিনিসকে রুমে ডুকাতে পারব না। আবার রুম থেকে কোন জিনিস  বাহিরে ফেলে দিতেও পারব না । কিন্তু আমি যেহেতু রুমের মধ্যে তাই রুমের জিনিসগুলোকে পরিবর্তন করতে পারব। 

তেমনি object কে সীল করলে আমরা object এ কোন property add বা remove করতে পারব না। তবে কোন property এর value পরিবর্তন করতে পারব।

যেমন আমরা সাধারন একটি object  লিখি

```javascript

const student = {
  name: 'Mr. Hablu',
  Roll: 01,
  Age: 15,
};
```
এখন object টি seal করে দেই।

```javascript
Object.seal(student);
```
এখন  object এ কোন property add, romove and modify করি।
```javascript
student.Gender = 'male'; // add new property
delete student.Age; // delete the age property
student.name = 'Mr. Messi'; // modify the name from Hablu to Messi
console.log(student); // show the output
```


এখন  আউটপুট দেখুন  , দেখবেন শুধু মাত্র নামটি পরিবর্তন হয়েছে কিন্তু কোন property নতুন করে add বা remove হয় নি।

---



02.**Object.freeze**

**Syntex**

```javascript
Object.freeze(objectName)
```

freeze মানে আমরা সবাই জানি।  ধরুন আপনার ডিপ ফ্রিজে একটি প্যাকেটে 5টি মাছ আছে। যতক্ষণ মাছগুলো বরফ অবস্থায় থাকবে অর্থাৎ freezing থাকবে ততক্ষণ কিন্তু আপনি কোন নতুন মাছ ওই প্যাকেটে রাখতে পারবেন না। ম্যাচগুলোর আপনি কোন পরিবর্তন ও করতে পারবেন না।
আবার 5 টি মাছ থেকে 1 টি মাছ ফেলেও দিতে পারবেন না কারণ সবগুলো বরফ হয়ে আছে।

তেমনি Object এর ক্ষেত্রেও একই কথা ।যখন আপনি কোন অবজেক্টকে freeze করবেন তখন
1. Object এর সাঠে কোন নতুন property যুক্ত করতে পারবেন না।
2. Object এর কোন property কে পরিবর্তন করতে পারবেন না।
3. Object এর কোন property কে delete করতে পারবেন না।

যেমন আমরা একটি object তৈরি করি।

```javascript
const person={
   name: 'Robeyoul',
   Age:33,
   height:'5.7'
}

```

এখন object টিকে freeze করি

```javascript
Object.freeze(person)
```

এখন এই object এর সাথে নতুন একটি property যোগ করার বা পরিবর্তন করা বা ডিলিট করার চেষ্টা করি।

```javascript

person.father='Altaf' // try to add new property
delete person.height // try to delete person height
person.Age=40 // try to change person age

console.log(person); // show the output

```

এখন আমরা আউটপুটটি খেয়াল করলে দেখতে পাব object এর সাথে নতুন কিছুই যোগ ও হয় নি, ডিলিট ও হয় নি আবার কিছু পরিবর্তন ও হয় নি। সব কিছু একই আছে।