# ✅ **EASY (Shadowing — 3 Problems)**

---

### **Problem 1 — Output?**

```js
let a = 5;

function test() {
  let a = 10;
  console.log(a);
}

test();
console.log(a);
```

### **Solution:**

```
10
5
```

Inner `a` shadows outer one.

---

### **Problem 2 — Output?**

```js
var x = 1;

function fun() {
  var x = 2;
  console.log(x);
}

fun();
console.log(x);
```

### **Solution:**

```
2
1
```

Function-level `var x` shadows global `x`.

---

### **Problem 3 — Output?**

```js
let a = 10;

{
  let a = 20;
  console.log(a);
}
console.log(a);
```

### **Solution:**

```
20
10
```

Block-level shadowing.

---
