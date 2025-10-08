# JavaScript-Algorithms-and-Data-Structures

---

# JavaScript Fundamentals — Syntax, Arrays, Strings, Sets/Maps & Big-O

## JavaScript Syntax Tips

* **`let` vs `const` vs `var`:**
  Use `const` by default. Use `let` if reassignment is required. Avoid `var`.
* **Arrow functions:**

  ```js
  const add = (a, b) => a + b;
  ```

  Shorter syntax, lexical `this`.
* **Destructuring:**

  ```js
  const [a, b] = [1, 2];
  const {x, y} = {x: 5, y: 10};
  ```
* **Default parameters:**

  ```js
  function greet(name = "World") { console.log(`Hello ${name}`); }
  ```
* **Spread & Rest operators:**

  ```js
  const nums = [1, 2, 3];
  const more = [...nums, 4, 5];
  function sum(...args) { return args.reduce((a, b) => a + b, 0); }
  ```

---

## Arrays

* **Creation & methods:**

  ```js
  const arr = [1, 2, 3];
  arr.push(4);      // add end
  arr.pop();        // remove end
  arr.shift();      // remove start
  arr.unshift(0);   // add start
  arr.slice(1, 3);  // copy section
  arr.splice(2, 1); // remove in place
  arr.map(x => x*2);
  arr.filter(x => x>2);
  arr.reduce((a,b)=>a+b,0);
  ```

* **Iterating:**

  ```js
  for (const n of arr) console.log(n);
  arr.forEach((v,i)=>console.log(i,v));
  ```

* **Copy vs reference:**
  `const b = arr` → same reference
  `const b = [...arr]` → shallow copy

---

## Strings

* **Common operations:**

  ```js
  const s = "hello";
  s.length;           // 5
  s.toUpperCase();    // "HELLO"
  s.slice(1, 3);      // "el"
  s.includes("ell");  // true
  s.split("");        // ["h","e","l","l","o"]
  s.replace("l", "L"); // "heLlo"
  ```

* **Template literals:**

  ```js
  const name = "Iren";
  console.log(`Hello, ${name}!`);
  ```

* **String immutability:**
  Strings can’t be modified in place; build a new one.

---

## Sets & Maps

### **Set**

* Unique values only.

  ```js
  const s = new Set([1, 2, 2, 3]);
  s.add(4); s.has(2); s.delete(1);
  console.log([...s]); // [1,2,3,4]
  ```

### **Map**

* Key–value pairs (keys can be any type).

  ```js
  const m = new Map();
  m.set("a", 1);
  m.set({id:1}, "object key");
  console.log(m.get("a")); // 1
  m.has("a"); m.delete("a");
  ```

---

## Big-O Complexity Overview

| Operation  | Array | Set/Map  | Notes                         |
| ---------- | ----- | -------- | ----------------------------- |
| Access     | O(1)  | —        | Random index lookup           |
| Search     | O(n)  | O(1) avg | Hash-based lookup for Set/Map |
| Insert End | O(1)* | O(1)     | Amortized for arrays          |
| Insert Mid | O(n)  | O(1)     | Shift required for arrays     |
| Delete     | O(n)  | O(1)     | Hash removal is constant avg  |

### Quick Rules of Thumb

* **Nested loops → O(n²)**
* **Binary search → O(log n)**
* **Divide & conquer recursion → O(n log n)**
* **Constant work → O(1)**
