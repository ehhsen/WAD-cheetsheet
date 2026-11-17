Mohsi   3019
Laiba   3020

CHEAT SHEET
1.DOM (Document Object Model): The DOM is a programming interface that represents an HTML document as a tree of
objects. It allows JavaScript to access, modify, add, and delete HTML elements dynamically.
Basic Syntax:
// Select an element by ID
Let heading = document.getElementById(“title”);
// Change its content
Heading.textContent = “Welcome”;
// Change its style
Heading.style.color = “blue”;
2.Anonymous Functions: An anonymous function is a function that does not have a name. It is commonly assigned to a
variable or passed as an argument to another function.
Example:
Const greet = function() {
 Console.log(“Hello!”);
};
Greet();


1. Function Returning a Function
In JavaScript, a function can return another function. The returned function can be stored in a variable and executed later.
This concept is commonly used in closures.
Example:
Function outer() {
 Return function() {
 Console.log(“Inner function”);
 };
}
2. Closure Functions: A closure is created when an inner function remembers and accesses variables from its
outer function, even after the outer function has finished executing.
Example:
Function outer() {
 Let message = “Hello”;
 Return function() {
 Console.log(message);
 };
}
Const inner = outer();
Inner(); // Hello
Here, the inner function remembers the message variable even after the outer function has finished executing.
3. Persistent Memory in a Function: Normally, local variables are initialized when a function is called. However,
closures allow a function to retain access to variables between multiple calls. This means the function can
remember its previous values instead of resetting them every time.
Example:
Function counter() {
 Let count = 0;
 Return function() {
 Count++;
 Return count;
 };
}
Const next = counter();
Console.log(next()); // 1
Console.log(next()); // 2
Console.log(next()); // 3
Explanation:
- count is a local variable of the outer function.
- - The inner function remembers count.
- Every time next() is called, the value increases.
- The value is preserved because of the closure.
Important Point:
Closures provide persistent memory by maintaining access to variables in their outer function’s scope. This memory lasts
as long as the closure remains accessible.


Method
getElementByld() == ID
getElementsByClassName() == Class
getElementsByTagName() == Tag
querySelector() == First CSS mach
querySelectorAll() == All CSS matches

innerHTML : Gets or changes HTML content, including HTML tags.
Example : element.innerHTML = "<h1>Hello</h1>";

textContent : Gets or changes only plain text, not HTML elements.
Example : element.textContent = "Hello";

DOM Manipulation : Used to create, modify, style, or remove HTML elements using JavaScript.
Example : document.createElement("p");
Const result = outer();
Result();

## Lec 15 (5 Nov) – Events

### 9.3 Events

#### Event handling steps
1. **Define** handler (a callback function)
2. **Register** it on an element with `addEventListener`
3. Event is **triggered** (user/page action)
4. Handler **executes**

```js
function simpleHandler() { alert("clicked"); }
const btn = document.querySelector("#btn");
btn.addEventListener("click", simpleHandler);      // named function

btn.addEventListener("click", function () { ... }); // anonymous function
btn.addEventListener("click", () => { ... });       // arrow function
```

#### NodeList vs Node
- Only a **single node** has `addEventListener()`, a **NodeList does not**
- Loop through the list and register on each node

```js
const btns = document.querySelectorAll("#list button");
for (let bt of btns) {
  bt.addEventListener("click", function () { ... });
}
```

#### Older approaches (avoid)
| Approach | Example | Problem |
|---|---|---|
| Inline | `<input onclick="handler()">` | Mixes HTML and JS, hard to maintain |
| Event property | `btn.onclick = function () {...}` | Only **one** handler per event per element |

#### Page loading and the DOM
Run DOM code only after the elements exist.

| Event | Fires when | Use |
|---|---|---|
| `window.load` | Whole page loaded (images, CSS too) | Slow, usually the wrong choice |
| `document.DOMContentLoaded` | HTML fully downloaded and parsed | **Preferred** |

```js
document.addEventListener("DOMContentLoaded", function () {
  // all DOM code here (can be placed in <head>)
});
```

#### Event object
- Browser creates it on trigger; receive it as the callback parameter (usually `e`)
- Common properties:
  - `e.target`: element that **generated** the event (always works)
  - `e.currentTarget`: element whose handler is **currently running**
  - `e.clientX`, `e.clientY`: cursor position (mouse events)
  - `e.key`: key pressed (keyboard events)

```js
function menuHandler(e) {
  e.target.classList.toggle("selected");
  console.log(e.clientX, e.clientY);
}
item.addEventListener("click", menuHandler);
```
- `this` inside a normal-function handler = the element; with an arrow function it is **not**
- A handler outside the loop can't use the loop variable (`item`) because it is out of lexical scope, so use `e.target`

#### Event propagation
When an event fires, it travels through the ancestors in two phases:

| Phase | Direction |
|---|---|
| **Capturing** | Outermost ancestor (`<html>`) → down to target |
| **Bubbling** (default) | Target → up to outermost ancestor |

```js
sec.addEventListener("click", handler, { capture: true }); // listen in capture phase
```

**Problem:** clicking an inner element also triggers parents' handlers.
**Fix:** `e.stopPropagation()` stops both capturing and bubbling.

```js
btn.addEventListener("click", function (e) {
  e.stopPropagation();   // parent handlers won't run
  incrementCount(e);
});
```

#### Event delegation
Put **one** listener on the parent and rely on bubbling, instead of a listener on every child.
- Saves memory
- Works for elements added or removed dynamically

```js
const parent = document.querySelector("#list");
parent.addEventListener("click", function (e) {
  // check the target is one of the children we want
  if (e.target && e.target.nodeName == "IMG") {   // nodeName is UPPERCASE
    doSomething(e.target);
  }
});



umar farooq 04072413022
•	e.target = clicked elements.
•	e.currentTarget = element with eventlistener.
•	e.toggle('open')= flips.
•	e.preventDefault() stops submission.
•	e.key = pressed key.
•	data-*: data-country="Peru" → el.dataset.country.
Mouse Event	Fires when
click / dblclick	Clicked / double clicked
mousedown / mouseup	Pressed / released 
mouseover / mouseout	Moved onto / off element
mousemove	Moved while over element

Keyboard	Fires when
keydown	Key pressed
keyup	Key released

Form Event	Fires when
blur / focus	Element loses / gains focus
change	textarea, <select> value changed
reset	Form reset
select	Text selected (block copy/paste)
submit	Form submitted (before server)



```
