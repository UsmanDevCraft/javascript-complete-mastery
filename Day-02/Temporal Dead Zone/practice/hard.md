# 🔥 **HARD (4 Problems)**

---

### **Problem 7 — Output?**

```js
function demo() {
  console.log(a);
  const a = 5;
}

demo();
```

### **Solution:**

```
ReferenceError
```

Inside the function, `a` is hoisted but uninitialized → TDZ.

---

### **Problem 8 — Output?**

```js
{
  let x = "outer";

  {
    console.log(x);  
    let x = "inner";
  }
}
```

### **Solution:**

```
ReferenceError
```

Even though outer `x` exists, the inner `x` starts a new TDZ, blocking access to the outer one.

---

### **Problem 9 — Output?**

```js
let a = 1;

{
  console.log(a);
  {
    let a = 2;
    console.log(a);
  }
}
```

### **Solution:**

```
1
2
```

Explanation:

* Outermost `{}` → has no `a`, so it uses global `a = 1`
* Inner `{}` → declares its own `a = 2`, so it prints `2`

No TDZ error because no access before declaration.

---

### **Problem 10 — Output?**

```js
let func = () => message;

let message = "Hello";

console.log(func());
```

### **Solution:**

```
Hello
```

Tricky but NO TDZ error.

Why?

* `func` only **returns** `message` *when executed*
* By the time `func()` runs, `message` is already initialized

TDZ would happen **only if you accessed `message` inside func BEFORE its declaration**, like:

```js
let func = () => message;
console.log(func()); // BEFORE let message = ...
let message = "Hello";
```

But here initialization happens first → safe.

---
