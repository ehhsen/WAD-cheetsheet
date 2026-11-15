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
