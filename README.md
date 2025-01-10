"# js1lecture3" 

# JavaScript Essentials: Closures, Promises, and Modules

This repository provides an overview of three essential topics in JavaScript: **Hoisting**, **Scope**, and **Temporal Dead Zone (TDZ)**. Each topic includes a code example and an explanation.

---

## 1. Hoisting

Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their scope during the compilation phase.

### Example:

```javascript
console.log(a); // undefined
var a = 5;

hoistedFunction(); // "This function is hoisted"
function hoistedFunction() {
    console.log("This function is hoisted");
}
```

### Explanation:
- Variable declarations using `var` are hoisted, but their values are not.
- Function declarations are fully hoisted, making them callable before their definition.

---

## 2. Scope

Scope determines the accessibility of variables, objects, and functions in different parts of the code. JavaScript has three types of scope: global, local, and block.

### Example:

```javascript
function scopeExample() {
    let localVariable = "I am local";
    if (true) {
        let blockVariable = "I am block-scoped";
        console.log(blockVariable); // "I am block-scoped"
    }
    // console.log(blockVariable); // ReferenceError: blockVariable is not defined
    console.log(localVariable); // "I am local"
}

scopeExample();
```

### Explanation:
- `let` and `const` have block scope, meaning they are accessible only within the block they are defined in.
- Variables declared with `var` have function scope and ignore block scope.

---

## 3. Temporal Dead Zone (TDZ)

The Temporal Dead Zone refers to the time between entering a scope and declaring a variable with `let` or `const`. Accessing the variable in this zone results in a `ReferenceError`.

### Example:

```javascript
console.log(tempVar); // ReferenceError: Cannot access 'tempVar' before initialization
let tempVar = "I exist now!";

function tdzExample() {
    console.log(innerVar); // ReferenceError
    const innerVar = "Now I exist";
}

tdzExample();
```

### Explanation:
- Variables declared with `let` and `const` are in the Temporal Dead Zone from the start of the block until their declaration is encountered.
- Accessing these variables before their declaration results in a `ReferenceError`.

---

## Conclusion

Understanding these three concepts—**Hoisting**, **Scope**, and **Temporal Dead Zone (TDZ)**—is essential for mastering JavaScript's behavior and avoiding common pitfalls. Each example above illustrates a key aspect of these concepts, helping you write more predictable and bug-free code.

Feel free to clone this repository and experiment with the examples!
