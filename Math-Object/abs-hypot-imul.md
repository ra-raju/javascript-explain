# abs, hypot, imul
---

1. **Math.abs()**

abs মানে absolute কোন বাস্তব সংখ্যা a এর পরম মান বা মডুলাস (প্রতীক: |x|) বলতে সংখ্যাটির শুধুমাত্র সাংখ্যিক মানকে বোঝায়। অর্থাৎ, +৫ এর পরম মান যেমন ৫ তেমনি -৫ এর পরম মানও ৫।
 x এর পরম মান সবসময়ই ধনাত্বক হবে, কখনোই ঋণাত্বক হতে পারবে না।
 
 ```javascript
var num1 = 5;
var num2 = -5;
var num3 = -0.005;
var num4 = 0.005;

console.log(Math.abs(num1)); // 5
console.log(Math.abs(num2)); // 5
console.log(Math.abs(num3)); // .005
console.log(Math.abs(num4)); // .005
```

2. **Math.hypot(x,y)**

এই মেথডের মাধ্যমে দুটি সংখ্যাকে স্কোয়ার করা হয়, তারপর সংখ্যা দুইটিকে যোগ করে তাদের স্কোয়ার রুট বের করা হয়।
যেমন : দুটি সংখ্যা 3 ও 4
     <p> 3<sup>2</sup>= 9 </p>
     <p> 4<sup>2</sup>= 16 </p>
     <p> &radic;(9+16)= 5 </p>
     
```javascript
var num1 = Math.hypot(3, 4);
var num2 = Math.hypot(5, 12);

console.log(num1); // 5
console.log(num2); // 13
```

3. **Math.imul(x,y)**

দুই আর্গুমেন্ট গুণ করে সেটা রিটার্ণ করে 

```javascript
var num1 = Math.imul(5, 6);
var num2= Math.imul(10, 10);

console.log(num1); // 30
console.log(num2); // 100
```


