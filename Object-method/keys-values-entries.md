# keys(), values(), entries()
---

1. **Object.keys()**

**Syntex**
```javascript
Object.keys(objectName)
```
এটি সাধারনত  object এর কী গুলোকে array আকারে return করে। 

```javascript
const person = {
  Name: 'Robeyoul Awal Raju',
  Roll: 101,
  Degree: 'BBA',
};

console.log(Object.keys(person));
```
```javascript
// output
[ 'Name', 'Roll', 'Degree' ]
```
---
02. **Object.values()**

**Syntex**

```javascript
Object.values(objectName)
```

এটি সাধারনত অবজেক্ট এর value গুলোকে  array আকারে return করে। আপনি যদি কোন object এর কি কি value আছে তা দেখতে চান তাহলে এটি ব্যবহার করতে পারেন।


```javascript
const person = {
  Name: 'Robeyoul Awal Raju',
  Roll: 101,
  Degree: 'BBA',
};

console.log(Object.values(person));
```

```javascript
// output
[ 'Robeyoul Awal Raju', 101, 'BBA' ]
```
---
03. **Object.entries()**

**Syntex**

```javascript
Object.entries(objectName)
```

এর মাধ্যমে আপনি  একটি object এর key এবং value গুলোকে key-value pair হিসাবে array আকারে পাবেন।

অর্থাৎ এর মাধ্যমে আপনি object এর key , value দুইটাই পাবেন।


```javascript
const person = {
  Name: 'Robeyoul Awal Raju',
  Roll: 101,
  Degree: 'BBA',
};

console.log(Object.entries(person));
```

```javascript
// output
[
  [ 'Name', 'Robeyoul Awal Raju' ],
  [ 'Roll', 101 ],
  [ 'Degree', 'BBA' ]
]
```