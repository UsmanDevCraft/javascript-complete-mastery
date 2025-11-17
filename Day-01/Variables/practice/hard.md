# 🔥🔥 HARD (Variables — 4 Problems)

---

### **Problem 7 — Error or Output?**

```js
let a = 10;

function test() {
  var a = 20;
  console.log(a);
}

test();
console.log(a);
```

### **Solution:**

```
20
10
```

Function scope hides the outside value.

---

### **Problem 8 — Tricky redeclaration**

```js
let a = 1;
{
  var a = 2;
}
console.log(a);
```

### **Solution:**

❌ **SyntaxError: Identifier 'a' has already been declared**

Reason:
`var a` tries to redeclare `let a` in the same global scope = **illegal shadowing**.

---

### **Problem 9 — Nested Scopes**

```js
let x = 1;

{
  let x = 2;
  {
    let x = 3;
    console.log(x);
  }
  console.log(x);
}

console.log(x);
```

### **Solution:**

```
3
2
1
```

Each block has its own `x`.

---

### **Problem 10 — Mutation check**

```js
const arr = [1, 2, 3];
arr.push(4);
arr = [5,6];
console.log(arr);
```

### **Solution:**

❌ Error:

```
TypeError: Assignment to constant variable
```

Push works, but reassigning the whole array doesn’t.

---
