# 🔥🔥 HARD (Hoisting — 4 Problems)

---

### **Problem 7**

```js
function test() {
  console.log(a);
  let a = 10;
}
test();
```

### **Solution:**

❌ ReferenceError
Because of TDZ inside function.

---

### **Problem 8**

```js
{
  console.log(a);
  var a = 5;
}
console.log(a);
```

### **Solution:**

```
undefined
5
```

`var` ignores block scope, so it behaves globally.

---

### **Problem 9 — Nested TDZ**

```js
console.log(a);
let a = 10;

{
  console.log(a);
  let a = 20;
}
```

### **Solution:**

❌ First error at line 1:

```
ReferenceError: Cannot access 'a' before initialization
```

Code never reaches inside block.

---

### **Problem 10 — Ultimate Trap**

```js
var x = 1;

function test() {
  console.log(x);
  var x = 2;
  function inner() {
    console.log(x);
  }
  inner();
}

test();
console.log(x);
```

### **Solution:**

```
undefined
2
1
```

Breakdown:

* `x` inside test is hoisted → local `x = undefined`
* First console → undefined
* Then x = 2
* inner() logs local x → 2
* Outside logs global x → 1

---
