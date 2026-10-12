# Lecture 7

The cascade decides which rule wins when CSS rules conflict.Three principles, in order: **Inheritance, Specificity, Location**.

## 1. Inheritance

- A property set on a parent is passed to its children.
- A property set directly on a child overrides the inherited one.
- Inheritable: font, color, list, text. Not inheritable: layout, border, background, margin/padding.
- Use `inherit` to force a non-inheritable property to be inherited.

```css
body { color: red; border: 8pt solid green; } /*text red, order not passed */
div { border: inherit; } /*border passed*/
```

## 2. Specificity

The more specific rule wins. A higher value overrides a lower one.

| Selector | Example | Value |
|---|---|---|
| Inline style | `style="color: red;"` | 1000 |
| ID | `#first` | 0100 |
| Class, attribute, pseudo-class | `.example`, `a:hover` | 0010 |
| Element, pseudo-element | `div`, `p::first-line` | 0001 |

Values add up: Count each type to get the value: `#footer .twitter a` = 1 ID + 1 class + 1 element = 0111 

```css
p { color: green; }        /* 0001 */
.last { color: blue; }     /* 0010      blue wins! */
```
## 3. Location

Used only when specificity is the same.

- The latest rule wins.
- Inline > embedded > external (embedded must come after `<link>`).
- Same property repeated in one block: the last one wins.

```css
p { color: red;}
p { color: pink}
```
/* Pink wins */
## `!important`

- Marked with `!important` and means *very* important.
- Overrides all rules irrespective of specificity or location.
- Rarely used.

```css
p { color: green !important; }
p { color: pink}
/* green wins */
```

## Order of Decision

1. No rule on the element: **inheritance**
2. Conflicting rules: **specificity**
3. Same specificity: **location**

# The Box Model

Every HTML element exists inside an **element box**. From inside to outside: **content → padding → border → margin**.

## Box properties:
- **Content**: the text or image, sized by `width` and `height`.
- **Padding**: space between content and border.
- **Border**: the line around the padding.
- **Margin**: space outside the border, between two elements.
- By default there is no border (border style is `none`), which is why it isn't visible.

- Width and height set the content area.
- The element's background fills out to its border.
- The margin is outside the border, so the parent's background shows through it.

**Border shorthand:** width, style, color

```css
border: 1px solid black;
```

**Padding and margin shorthand:** Top, Right, Bottom, Left (TRBL, clockwise)

```css
padding: 10px 20px 10px 20px; /* top right bottom left */
padding: 10px 20px;           /* top/bottom  left/right */
padding: 10px;                /* all four sides */
```

## Block vs Inline Elements

| | Block | Inline |
|---|---|---|
| Examples | `<p>`, `<div>`, `<h2>`, `<ul>`, `<table>` | `<em>`, `<a>`, `<img>`, `<span>` |
| Layout | Starts on a new line, stacked top to bottom | Flows left to right on the same line |
| Width | Fills the full width of its parent by default | Only as wide as its content |
| Wrapping | n/a | Moves to the next line when there is no space, and reflows on resize |
| Margin, padding, border | Work on all four sides | Left/right work normally. Top/bottom margin has no effect, and top/bottom padding and border don't push other lines away |
| `width` / `height` | Apply | Don't apply (except `<img>`) |

- A block can contain other blocks (stacked) or inline content (left to right).

### Background

- `background-color` — sets background color. **Values:** color name, HEX, RGB, RGBA, HSL, HSLA, `transparent`
- `background-image` — sets background image. **Values:** `url()`, `linear-gradient()`, `radial-gradient()`, `none`
- `background-repeat` — controls image repetition. **Values:** `repeat`, `repeat-x`, `repeat-y`, `no-repeat`, `space`, `round`
- `background-position` — controls image position. **Values:** `left`, `right`, `top`, `bottom`, `center`, percentages, length units
- `background-size` — controls image size. **Values:** `auto`, `cover`, `contain`, length, percentage
- `background-attachment` — controls how the background scrolls. **Values:** `scroll`, `fixed`, `local`
- `background` — shorthand for background properties.

```css
div {
    background-color: pink;
    background-image: url("image.jpg");
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}
```

## Gradients

Gradients are images, so they are set with `background-image`.

- **Linear**: color changes along a line.
- **Repeating linear**: the linear pattern repeats.
- **Radial**: color spreads outward from a center point.

```css
background-image: linear-gradient(to right, red, blue);
background-image: repeating-linear-gradient(red 0, blue 20px);
background-image: radial-gradient(circle, red, blue);
```

