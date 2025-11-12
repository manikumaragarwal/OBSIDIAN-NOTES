## 🧠 Mental Model Summary

```
JavaScript Functions
├── Function Declarations (always named, hoisted)
└── Function Expressions (anonymous or named, not hoisted)
    ├── Regular Function Expressions
    │   ├── Anonymous: function() {}
    │   └── Named: function name() {}
    └── Arrow Function Expressions (always anonymous)
        ├── () => {}
        ├── x => x * 2
        └── (a, b) => a + b

Usage Contexts (for Function Expressions):
├── Variable Assignment
├── Callbacks (events, async, array methods, promises)
├── IIFEs (Immediately Invoked)
├── Higher-Order Functions (parameters/returns)
├── Object Methods
├── Constructor/Factory Patterns
└── Closures
```
---
## 🏗️ Two Foundation Types

### 1. Function Declaration
- **Must be named** (syntax requirement)
- **Hoisted** (available before declaration)
- Creates binding in containing scope

```javascript
function myFunction() {
    return "I'm a declaration";
}
```

### 2. Function Expression
- **Can be anonymous or named**
- **Not hoisted** (only variable is hoisted, not the function)
- Function is created at runtime

```javascript
// Anonymous
const func1 = function() { return "anonymous"; };

// Named
const func2 = function namedFunc() { return "named"; };
```

---

## 🎭 Function Expression Usage Patterns

Function expressions can be used in many different ways:

### **Assignment Patterns**
- **Variable Assignment**: `const myFunc = function() {}`
- **Object Method**: `const obj = { method: function() {} }`
- **Array Element**: `const arr = [function() {}]`

### **Callback Patterns**
- **Event Handlers**: `button.onclick = function() {}`
- **Async Operations**: `setTimeout(function() {}, 1000)`
- **Array Methods**: `arr.map(function(x) { return x * 2 })`
- **Promise Handlers**: `.then(function(data) {})`

### **Immediate Execution**
- **IIFE**: `(function() { console.log("immediate!"); })()`
- **Module Pattern**: `const module = (function() { return {...}; })()`

### **Higher-Order Function Patterns**
- **Function as Parameter**: `function process(callback) { callback(); }`
- **Function as Return Value**: `function makeFunc() { return function() {}; }`
- **Closures**: Functions that remember their lexical environment

### **Constructor Patterns**
- **Constructor Function**: `const obj = new (function Constr() {})`
- **Factory Function**: `function createFunc() { return function() {}; }`

---

## 🏹 Arrow Functions (Special Type of Expression)

Arrow functions are **always anonymous function expressions** with special syntax:

```javascript
// Arrow function expressions
const arrow1 = () => "hello";
const arrow2 = (x) => x * 2;
const arrow3 = (a, b) => { return a + b; };

// Used in same patterns as regular function expressions
arr.map(x => x * 2);                    // Callback
setTimeout(() => console.log("hi"), 100); // Callback
```

---
## 🎯 Key Insight

**The "usage patterns" (callbacks, IIFEs, etc.) are not different types of functions - they're different contexts where function expressions are used!**

The function type is determined by **how it's declared** (declaration vs expression), not by **how it's used**.
