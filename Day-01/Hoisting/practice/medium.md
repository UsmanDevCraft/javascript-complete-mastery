# 🔥 MEDIUM (Hoisting — 3 Problems)

---

### **Problem 4**

```js
console.log(a);
var a = 10;
console.log(a);
```

### **Solution:**

```
undefined
10
```

First log prints hoisted value, second prints assigned value.

---

### **Problem 5**

```js
console.log(x);
var x = 5;
function test() {
  console.log(x);
  var x = 20;
}
test();
```

### **Solution:**

```
undefined
undefined
```

Reason:
`x` inside test is hoisted separately.

---

### **Problem 6**

```js
sayHi();
var sayHi = function() {
  console.log("Hey!");
}
```

### **Solution:**

❌ TypeError:

```
sayHi is not a function
```

`sayHi` gets hoisted as `undefined`.

---
