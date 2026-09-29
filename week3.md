I am Sayed Mehmood
# CSS & DOM Cheat Sheet

## 1. Selectors

### Element Selector

Selects HTML elements by tag.

```css
p { color: red; }
```

### Class Selector

Starts with `.`. Used for multiple elements.

```css
.box { color: blue; }
```

### ID Selector

Starts with `#`. Normally unique.

```css
#header { color: green; }
```

### Attribute Selector

Selects by attribute.

```css
input[type="text"] { color: red; }
```

| Symbol        | Meaning          |
| ------------- | ---------------- |
| `[attr]`      | Attribute exists |
| `[attr="x"]`  | Exact value      |
| `[attr^="x"]` | Starts with      |
| `[attr$="x"]` | Ends with        |
| `[attr*="x"]` | Contains         |

---

## 2. DOM

**DOM = Document Object Model**

* Represents HTML as a **tree of elements/nodes**.
* JavaScript uses DOM to access/change HTML.

```js
document.getElementById("id");
document.querySelector(".class");
document.querySelectorAll("p");
```

### Change Content

```js
element.textContent = "Hello";
element.innerHTML = "<b>Hello</b>";
```

### Change CSS

```js
element.style.color = "red";
```

---

## 3. Pseudo-Class

Used for an **element's state**.

```css
a:hover { color: red; }
input:focus { border: 2px solid blue; }
```

Common:

```text
:hover
:focus
:active
:visited
:first-child
:last-child
:nth-child()
:not()
```

**Remember:** `:` → Pseudo-class

---

## 4. Pseudo-Element

Styles a **part of an element**.

```css
p::first-letter {
    font-size: 30px;
}
```

Common:

```text
::before
::after
::first-letter
::first-line
::selection
```

**Remember:** `::` → Pseudo-element

---

## 5. Serif & Sans-Serif

### Serif

Has decorative strokes.

```css
font-family: serif;
```

Examples: `Georgia`, `Times New Roman`

### Sans-Serif

No decorative strokes.

```css
font-family: sans-serif;
```

Examples: `Arial`, `Verdana`

**Easy:**
`Serif = strokes`
`Sans-serif = no strokes`

---

## 6. Selector Quick Revision

```text
p       → Element
.box    → Class
#box    → ID
[attr]  → Attribute
:hover  → Pseudo-class
::after → Pseudo-element
```
content added by muhammad khizar: Note: Lecture 6 was assigned to me (M.Khizar (04072413008)) and I completed my task , unfortunately , 007 (Syed Mehmood) copied pasted same task of mine
Lecture.06

=>Selectors types:

Universal Selector -> *{}
Element Selector -> element_name {}
Class Selector -> .{}
Attribute Selector -> [attribute_name] {}
=> Regular Expressions:

'$' - end of line ( e.g: href '$' = ".pdf" )
'^' - start of line ( e.g: href '^' = "http" )
finding specific word anywhere ( e.g: href '*' = "qau" ) (finding 'qau' within qau website)
(tilda) - matching an exact word '( e.g: href '' = "books" )'
=>Pseudo-Class selectors: . it describes the "state" of an element . e.g. a:link , a:visited , a: hover, :first/last-child , :nthchild . syntax: ':' + class

=>Pseudo-element selectors: . it describes the position of an element . e.g. :first-letter , :first-line

=>Contextual Selectors (Combinators): . '>' - direct child . '+' - adjacent sibling . '~' - general sibling

=>Specificity: Precedence/Sequence of applying styles
