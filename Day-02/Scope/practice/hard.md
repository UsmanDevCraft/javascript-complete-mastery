# ✅ **HARD (4 Problems)**

---

### **7) Trick with Hoisting + var + Function Scope**

```js
console.log(a);
var a = 20;

function show() {
  console.log(a);
  var a = 10;
  console.log(a);
}

show();
console.log(a);
```

✔ Predict all outputs step-by-step.
✔ Understand hoisting inside a function.

---

### **8) Block Scope + Closures**

```js
let funcs = [];

for (let i = 0; i < 3; i++) {
  funcs.push(function() {
    console.log(i);
  });
}

funcs[0]();
funcs[1]();
funcs[2]();
```

✔ Predict output and explain why each function logs the correct value.

---

### **9) Scope Shadowing**

```js
let value = 100;

function calc() {
  console.log(value);

  let value = 50;

  console.log(value);
}

calc();
```

✔ Will this run or throw an error?
✔ Explain why (hint: TDZ + shadowing).

---

### **10) Scope Chain with nested functions**

```js
let x = 1;

function a() {
  let x = 2;

  function b() {
    let x = 3;

    function c() {
      console.log(x);
    }

    c();
  }

  b();
}

a();
```

✔ Which `x` does function `c` use and why?
✔ Explain using lexical scope + scope chain.

---
