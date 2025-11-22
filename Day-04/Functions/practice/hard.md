# 🔥 **HARD (Functions — 4 Problems)**

---

### **Problem 1 — Arrow Function LEXICAL THIS trap**

```js
function Person() {
  this.age = 20;
  setTimeout(() => {
    console.log(this.age);
  }, 0);
}

new Person();
```

### **Solution:**

```
20
```

Arrow captures `this` from constructor.

---

### **Problem 2 — Normal Function THIS trap**

```js
const obj = {
  value: 100,
  show: function () {
    function inner() {
      console.log(this.value);
    }
    inner();
  },
};

obj.show();
```

### **Solution:**

```
undefined
```

`inner()` is called without object → `this = global` → undefined.

---

### **Problem 3 — Function Returning Function (Closure)**

```js
function outer() {
  let x = 5;
  return function inner() {
    console.log(x);
  };
}

const fn = outer();
fn();
```

### **Solution:**

```
5
```

Inner function closes over outer scope.

---

### **Problem 4 — Arrow Lacks `arguments`**

```js
const test = () => {
  console.log(arguments.length);
};

test(1, 2, 3);
```

### **Solution:**

```
ReferenceError: arguments is not defined
```

Arrow functions do NOT have `arguments`.

---
