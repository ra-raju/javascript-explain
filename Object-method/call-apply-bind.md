# call(), apply() and bind()

ধরুন আপনি ডিম খেতে চান কিন্তু আপনার ঘরে ডিম নেই। তাই আপনি দোকান থেকে ডিম নিয়ে আসবেন। এখন ডিম আপনি দুই ভাবে আনতে পারেন, ১. দুই হাতে দুইটি ডিম আনতে পারেন। আবার একটি প্যাকেট এ করে আনতে পারেন। 

ডিম আনার পর আপনি ডিম সাথে সাথে খেতে পারেন আবার পরেও খেতে পারেন। 


এখন আপনি যদি ডিম সাথে সাথে খান আর দুই হাতে দুইটি ডিম নিয়ে আসেন তাহলে সেটি call.
আবার আপনি যদি ডিম সাথে সাথে খান আর দুইটি ডিম প্যাকেট অর্থাৎ array এর মাধ্যমে  নিয়ে আসেন তাহলে সেটি apply.

আবার যদি আপনি ডিমটি পরে খেতে চান আর দুই হাতে দুইটি ডিম নিয়ে আসেন তাহলে তা bind

অর্থাৎ মূলকথা হল ,
যখন call method ব্যবহার করবেন তখন আপনাকে প্যারামিটার গুলো (,) এর মাধ্যমে দিতে হবে, যদি প্যারা মিটার না থাকে তাহলে কিছু দিতে হবে না। 
যখন apply method ব্যবহার করবেন তখন আপনাকে প্যারামিটার গুলো [](array) এর মধ্যে দিতে হবে, যদি প্যারা মিটার না থাকে তাহলে কিছু দিতে হবে না। 

যখন bind method ব্যবহার করবেন তখন আপনাকে প্যারামিটার গুলো (,) এর মাধ্যমে দিতে হবে, যদি প্যারা মিটার না থাকে তাহলে কিছু দিতে হবে না। 


কিন্তু সাথে সাথে ডিম খাওয়ার মত ,যদি  আপনি চান আপনার function টি সাথে সাথে call করবেন তাহলে আপনি call বা apply ব্যবহার করবেন।

আবার যদি চান আপনি function টি পরে call করবেন তাহলে তাহলে bind ব্যবহার করবেন।

---

এখন practically  বুঝার চেষ্টা করি।

ধরুন আপনার  দুইটি object আছে।  একটি parent object অন্যটি child object.  আপনার parent object এ একটি method আছে যা child object এ নাই। এখন আপনি আপনার  child object এও সেই method টি ব্যবহার করতে চান। তাহলে আপনি apply, call এবং bind ব্যবহার করতে পারেন। apply, call, and bind সাধারণত একই কাজ করে শুধু একটু ভিন্ন ভাবে।

---

```javascript
const parent = {
  name: 'Mr. XYZ',
  age: 70,
  income: 50000,
  netIncome(houseRent, mealCost, electricBill) {
    const moneyInHand = this.income - houseRent - mealCost - electricBill;
    console.log(moneyInHand);
    // return moneyInHand;
  },
};
```
```javascript
const child = {
  name: 'Mr. ABC',
  age: 20,
  income: 40000,
};
```
দেখুন parent object এ netIncome নামে একটি মেথড আছে । এখন আমরা চাই  এই মেথডটি আমি child object ব্যবহার করব।


1. **apply**

**Syntex**

`parentObj.apply(childObj, [parameter])`

```javascript
parent.netIncome.apply(child, [10000, 7000, 3000]); // output: 20000
```
2. **call**

**Syntex**

`parentObj.call(childObj, parameter1, parameter2, ...)`

```javascript
parent.netIncome.call(child, 10000, 7000, 3000); // output: 20000
```
3. **bind**

**Syntex**

`parentObj.call(childObj, parameter1, parameter2, ...)`

```javascript
const netIncome= parent.netIncome.bind(child, 10000, 7000, 3000); 
netIncome() // output: 20000
```

উপরে লক্ষ্য করুন, call ও apply এ আমরা সরাসরি আউটপুট পাচ্ছি কিন্তু bind এর ক্ষেত্রে প্রথমে একটি variable এ function টি রাখছি তারপর আমাদের প্রয়োজন মত কল করছি। যদি কল না করি তাহলে তা কোন কিছু পরিবর্তন করবে না।

---

আমরা চাইলে সাধারন একটি function ও এগুলোর মাধ্যমে বাবহার করতে পারি।

আমরা একটি function লিখি যা আমাদের নাম ও বয়স প্রিন্ট করবে।

```javascript
function myDetails() {
  console.log(`My name is ${this.name}. I am ${this.age} years old`);
}
```

একটি নাম ও বয়স যুক্ত object লিখিঃ 

```javascript
const student = {
  name: 'Mrs. Comola',
  age: 30,
};
```

এখন আমরা উপরের fucntion টি  অবজেক্ট এর সাথে ব্যবহার করব।

*using apply method*

```javascript
myDetails.apply(student);
// My name is Mrs. Comola. I am 30 years old
```
*using call method*

```javascript
myDetails.call(student);
// My name is Mrs. Comola. I am 30 years old
```

*using bind method*

```javascript
const details = myDetails.bind(student);
details();
// My name is Mrs. Comola. I am 30 years old
```

function এ যেহেতু কোন প্যারা মিটার নাই তাই কোন value ও ব্যবহার করা হয় নি।
