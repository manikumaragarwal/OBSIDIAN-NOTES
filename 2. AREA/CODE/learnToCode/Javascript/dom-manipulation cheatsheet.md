---
id: dom-manipulation cheatsheet
tags: []
---

#### 🔎 Selecting Elements

```js
const div = document.querySelector("div"); // first matching
const allButtons = document.querySelectorAll("button"); // all matching

const byId = document.getElementById("myId");
const byClass = document.getElementsByClassName("myClass");
const byTag = document.getElementsByTagName("p");
```

---

#### 🧱 Creating Elements

```js
const newDiv = document.createElement("div");
```

---

#### 🖋️ Adding Text or HTML Content

```js
element.textContent = "Hello"; // Just text
element.innerHTML = "<strong>Hi</strong>"; // Parses HTML
```

⚠️ `innerHTML` can be risky if you insert user input → XSS attack alert!

---

#### 📦 Appending & Inserting Elements

```js
parent.appendChild(child); // Add at end
parent.insertBefore(newNode, refNode); // Insert before
element.append("text", anotherElement); // Add multiple things
```

---

#### 🗑️ Removing Elements

```js
element.remove(); // Clean and easy
```

---

#### 🎨 Styling Elements

```js
element.style.color = "red"; // Inline style
element.classList.add("big"); // Add class
element.classList.remove("small"); // Remove class
element.classList.toggle("hidden"); // Toggle on/off
```

---

#### 🎯 Adding Event Listeners

```js
button.addEventListener("click", () => {
  alert("Button clicked!");
});
```

- Common events: `'click'`, `'mouseover'`, `'keydown'`, `'submit'`, etc.

---

#### 📋 Example: Create and Append Button

```js
const btn = document.createElement("button");
btn.textContent = "Click me!";
btn.classList.add("fancy");
btn.addEventListener("click", () => {
  alert("Fancy click!");
});
document.body.appendChild(btn);
```

---

#### 🧪 Event Object

```js
button.addEventListener("click", (e) => {
  console.log(e.target); // The element that was clicked
});
```

---

### 🧼 Clean Practices

- Prefer `textContent` over `innerHTML` unless you need HTML formatting.
- Use `addEventListener()` instead of inline `onclick`.
- Keep JS and HTML separate. Don’t hardwire logic into HTML.

---
