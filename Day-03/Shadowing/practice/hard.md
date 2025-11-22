# 🔥 **HARD (Shadowing — 4 Problems)**

---

### **Problem 7 — Output?**

```js
var a = 1;

function test() {
  console.log(a);
  var a = 2;
  console.log(a);
}

test();
```

### **Solution:**

```
undefined
2
```

`var a` inside function shadows the global `a`, but due to hoisting its value is `undefined` until assigned.

---

### **Problem 8 — Output?**

```js
let x = 5;

{
  const x = x + 5;
  console.log(x);
}
```

### **Solution:**

```
ReferenceError
```

The inner `x` shadows the outer `x`, so the right side `x + 5` tries to access the inner variable (not outer one).
But inner `x` is in TDZ → error.

---

### **Problem 9 — Output?**

```js
let a = 1;

function one() {
  let a = 2;

  {
    var a = 3;   // is this legal?
    console.log(a);
  }
}

one();
```

### **Solution:**

```
SyntaxError: Identifier 'a' has already been declared
```

❌ Illegal shadowing:

* `let a` is function scoped (inside `one`)
* `var a` also belongs to the same function scope
* Not allowed.

---

### **Problem 10 — Output?**

```js
let a = 10;

function outer() {
  var a = 20;

  {
    let a = 30;
    console.log(a);
  }

  console.log(a);
}

outer();
console.log(a);
```

### **Solution:**

```
30
20
10
```

Breakdown:

* Block `let a = 30` shadows function-level `var a = 20`
* Function-level `var a` shadows global `let a = 10`

---
