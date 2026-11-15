## Lecture 13: JavaScript Arrays & Objects AMNA ABAIDULLAH'S PART

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
