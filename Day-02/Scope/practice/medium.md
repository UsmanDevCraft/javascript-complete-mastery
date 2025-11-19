# ✅ **MEDIUM (Scope — 3 Problems)**

---

### **Problem 4 — Function Scope (var) Output?**

```js
function test() {
  var name = "Usman";
  if (true) {
    var name = "Ali";
  }
  console.log(name);
}

test();
```

### **Solution:**

```
Ali
```

`var` ignores block scope; it reassigns the same variable.

---

### **Problem 5 — Block Scope Shadowing Output?**

```js
function demo() {
  let count = 1;

  if (true) {
    let count = 2;
    console.log(count);
  }

  console.log(count);
}

demo();
```

### **Solution:**

```
2
1
```

The inner `count` shadows the outer one.

---

### **Problem 6 — Lexical Scope Output?**

```js
let msg = "hello";

function outer() {
  let msg = "outer msg";

  function inner() {
    console.log(msg);
  }

  inner();
}

outer();
```

### **Solution:**

```
outer msg
```

Inner function uses the variable from where it was **defined**, not where it was called.

---
