## JavaScript - Language Fundamentals

### Variables and Data Types

- **let:** can be reassigned, block scoped. This is the default choice.
- **const:** can't be reassigned, must be given a value right away. Objects and arrays declared with it can still be changed inside.
- **var:** the old way. Function scoped and can be redeclared. Just don't use it.
- **Primitive types:** `number`, `string`, `boolean`, `undefined`, `null`, `symbol`, `bigint`. Everything else (arrays, objects, functions) is an object.
- **Template literals:** backticks let you use variables into a string, like `` `Hello ${name}` ``.
- **Checking types:** `typeof x`.

| Code | Result |
| ---- | ------ |
| `"5" + 2` | `"52"` (+ joins as soon as a string is involved) |
| `"5" - 2` | `3` (every other operator converts to number) |
| `Number("abc")` | `NaN` |
| `NaN === NaN` | `false`, so use `Number.isNaN(x)` |
| `5 == "5"` | `true` (loose, converts first) |
| `5 === "5"` | `false` (strict, so use this one) |

### Conditionals

- **if / else if / else:** same as C++ or Java.
- **Falsy values:** `false`, `0`, `""`, `null`, `undefined`, `NaN`. Everything else is truthy, even `"0"`, `"false"`, `[]` and `{}`.
- **switch:** compares with `===`. Forget `break` and it keeps running into the next case.
- **Ternary:** `cond ? a : b`, works like C++ but gives you a value you can store.
- **`&&` and `||`:** these return one of the actual values, not just true/false. `a || b` gives `a` if it's truthy, else `b`, so it's used for defaults. `a && b` gives `b` only if `a` is truthy.


### Loops

- **for, while & do..while:** Nothing newly (surely)
- **break / continue:** work as expected.
- **For-In & For-Of:** `for (let key in obj)` loops through object property keys; `for (let val of arr)` loops through iterable values. 


### Arrays

Creation: `const arr = [1, "a", true];` Values can be of any type and can be nested.
Index starts at 0. Last item: `arr[arr.length - 1]`. 2D array: `grid[row][col]`.

| Method                   | Purpose                                           |
| ------------------------ | ------------------------------------------------- |
| push(x) / pop()          | Add / remove at the end. Changes original.        |
| unshift(x) / shift()     | Add / remove at the start. Changes original.      |
| splice(i, n)             | Remove or insert in the middle. Changes original. |
| sort() / reverse()       | Sort / flip the order. Changes original.          |
| slice(a, b)              | Copy a part. Original stays the same.             |
| concat(b)                | Join two arrays. Original stays the same.         |
| join(",") / split(",")   | Array to string / string to array.                |
| includes(x) / indexOf(x) | true or false / position (-1 if not found).       |
| Array.isArray(x)         | Check if x is an array.                           |

### Looping

| Loop                                 | Usage                                     |
| ------------------------------------ | ----------------------------------------- |
| for (let i = 0; i < arr.length; i++) | When the index is needed.                 |
| for (const v of arr)                 | Gives each VALUE.                         |
| for (const k in obj)                 | Gives each KEY. Use obj[k] for the value. |

Array of objects with a condition:

```js
for (const c of cities) {
  if (c.continent === "NA") {
    console.log(c.name);
  }
}
```

Here c is one object each time. For a 2D array, put one for...of loop inside another.

### Destructuring and Spread

| Syntax                                    | Purpose                                             |
| ----------------------------------------- | --------------------------------------------------- |
| `const [a, b] = arr;`                     | Array: matched by POSITION.                         |
| `const [a, , c] = arr;`                   | Skip an item with an empty comma.                   |
| `const [h, ...rest] = arr;`               | rest collects the remaining items. It must be last. |
| `[a, b] = [b, a];`                        | Swap two variables.                                 |
| `const { id, name } = obj;`               | Object: matched by KEY NAME.                        |
| `const { name: n } = obj;`                | Rename: n holds the name.                           |
| `const { id, location: { city } } = obj;` | Nested object in one line.                          |
| `[...a, ...b]`                            | Spread: join arrays. `[...a]` copies an array.      |
| `{ ...x, ...y }`                          | Spread: join objects. The later key wins.           |

### Objects and JSON

```js
const student = {
  name: "Ali",
  id: 123,
  colors: ["blue", "pink"],
  courses: [{ code: 101, title: "PSP" }],
};
```

| Syntax                                     | Purpose                                          |
| ------------------------------------------ | ------------------------------------------------ |
| student.name                               | Dot notation. Normal choice.                     |
| student["name"]                            | Bracket notation. The key can be a variable.     |
| student.courses[0].title                   | Nested data. Read one step at a time.            |
| student.age = 20 / delete student.age      | Add / remove a property any time.                |
| output: function () { return this.price; } | Function inside an object. this is the object.   |
| JSON.stringify(obj)                        | Object to string. Used to send data to a server. |
| JSON.parse(str)                            | String to object. Used after receiving data.     |

JSON is a text format for sending data. It replaced XML.
Flow: form data, object, stringify, server, string, parse, show on page.


### Functions

Three ways to write one:

```js
function add(a, b) { return a + b; }            // declaration
const add2 = function (a, b) { return a + b; }; // expression
const add3 = (a, b) => a + b;                    // arrow
```

- **Hoisting:** declarations can be called before the line where they're written. Expressions and arrows can't.
- **return:** no return means the function gives back `undefined`.
- **Arguments:** missing ones become `undefined`, extra ones are ignored. No error either way.
- **Default values:** `function greet(name = "friend") {}`
- **Rest parameter:** `function sum(...nums) {}` collects all the extra arguments into an array. It has to be the last parameter.
- **Arrow functions:** with no braces the value is returned automatically.
- **Callbacks:** functions are values, so you can pass one into another function.
- **Passing data in:** primitives are copied, so changing them inside doesn't affect the outside. Objects and arrays are passed as references, so changing them inside **does** change the original.

### Scope and Closures

| Scope | Where it applies |
| ----- | ---------------- |
| Global | Declared outside everything, visible everywhere |
| Function | Declared inside a function, invisible outside it |
| Block | `let`/`const` inside `{ }`, gone after the closing brace |

- **var ignores blocks:** it only respects function scope, which is why people avoid it.
- **Lexical scope:** an inner function can read variables from the functions around it, but the outer one can't read the inner one's.
- **Hoisting of variables:** `var` is hoisted and starts as `undefined`. `let` and `const` are hoisted too, but touching them before their declaration line throws an error.
- **Closure:** a function that remembers the variables from where it was created, even after the outer function has finished.

```js
function makeCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const c = makeCounter();
c(); // 1
c(); // 2
```

`count` is basically private here. Nothing outside can touch it except the returned function.


### Important things

| Topic               | Remember                                                            |
| ------------------- | ------------------------------------------------------------------- |
| const               | An array or object can still change. const only stops re-assigning. |
| b = a               | Does NOT copy. Both share one array. Use `[...a]`.                  |
| Spread copy         | Shallow. Nested arrays and objects are still shared.                |
| sort()              | Sorts as text. `[10, 9, 1].sort()` gives `[1, 10, 9]`.              |
| splice / slice      | splice changes the original. slice does not.                        |
| for...of / for...in | of gives values. in gives keys.                                     |
| Destructuring       | Array is by position. Object is by name.                            |
| typeof []           | Gives "object". Use Array.isArray().                                |
| {} === {}           | false. Objects are compared by reference.                           |
| Missing key         | Gives undefined. But undefined.x crashes.                           |
| JSON                | Needs double quotes. stringify skips functions.                     |
| ...                 | Spread in literals. Rest in function parameters.                    |
