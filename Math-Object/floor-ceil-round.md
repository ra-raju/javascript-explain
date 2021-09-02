# floor, ceil, round
---

1. **Math.floor()**

এই মেথডের কাজ হচ্ছে দশমিক সংখ্যাকে ইন্টিজার সংখ্যায় নিয়ে যাওয়া। যেমন ধরি আমাদের একটা সংখ্যা আছে ১০.১০ এরকম। এখন এই মেথড সেই সংখ্যাকে দশমিক বাদ দিয়ে ইন্টিজার নাম্বারে নিয়ে যাবে। এক্ষেত্রে ১০.১০ হবে ১০ |
যদি এই সংখ্যাটা ১০.১০ না হয়ে ১০.৯৯হতো তাহলে Math.floor() ইউজ করলে সেটার রেজাল্ট কি হতো? হ্যাঁ এটা পুরো .৯৯ ই বাদ দিয়ে দিবে। আর ফলাফল হবে শুধুমাত্র ১

```javascript
var num1 = 10.99;
var num2 = 10.01;

console.log(Math.floor(num1)); // 10
console.log(Math.floor(num2)); // 10
```

2. **Math.trunc()**

same to Math.floor

```javascript
var num1 = 10.99;
var num2 = 10.01;

console.log(Math.trunc(num1)); // 10
console.log(Math.trunc(num2)); // 10
```


3. **Math.ceil()**

ceil মানে ceiling অর্থাৎ উপরের অংশ । অর্থাৎ কোন দশমিক সংখ্যাকে তার থেকে বড় integer সংখ্যায় রূপান্তর করে।

```javascript
var num1 = 10.99;
var num2 = 10.02;

console.log(Math.ceil(num1)); // 11
console.log(Math.ceil(num2)); // 11
```
4. **Math.round()**

এটি সাধারন দশমিক সংখ্যার কাজ করে। কোন দশমিক সংখ্যা যদি .৫ বা তার বড় হয় তাহলে  সংখ্যাটি ১ বৃদ্ধি পায় যদি .৫ এর ছোট হয় তাহলে কোন পরিবর্তন হয় না।

```javascript
var num1 = 10.41;
var num2 = 10.51;

console.log(Math.round(num1)); // 10
console.log(Math.round(num2)); // 11
```

Math.floor আর Math.ceil মনে রাখার কৌশলঃ

ধরুন আপনি একটা সংখ্যা। আপনি একটা ঘরের মধ্যে দাড়িয়ে আছেন। আপনার নিচে হল floor আর উপরে হল ceiling
। এখন আপনি যদি নিচের কথা ভাবেন তাহলে  এক কমে যাবে আবার যদি ceiling এর কথা ভাবেন তাহলে এক বেড়ে যাবে।