# ✅ **MEDIUM (3 Problems)**

---

### **4) Function Scope (var)**

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

✔ What will be logged?
✔ Why does this happen?

---

### **5) Block Scope (let) inside function**

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

✔ Explain both outputs.

---

### **6) Lexical Scope Example**

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

✔ What will be printed?
✔ Which `msg` does inner() use and why?

---
