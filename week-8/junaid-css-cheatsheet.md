## **CSS Properties & Layouts**

### **Collapsing Margins:**
  **Vertical Margins (Sibling Boxes):** They do not add together. They collapse, and the larger margin wins.
  **Horizontal Margins:** They do not collapse. They add together.

### **Gradients:**
Gradients are applied to `background-image` or `background`, never to `background-color`.
  **Linear Gradient:** Moves from one side/corner to another.
    **Syntax:** `linear-gradient(direction, color-1, color-2)`
  **Radial Gradient:** Radiates outward from a specific point (circular/elliptical).
    **Syntax:** `radial-gradient(shape at position, color-1, color-2)`
  **Repeating Gradient:** Repeats a gradient pattern.
    **Syntax:** `repeating-linear-gradient(direction, color-1 start, color-1 end, color-2 start, color-2 end)`

### **Border-Box (Box Sizing):**
When setting the width of an element, padding and borders expand its total size. To prevent this, apply `border-box` to all elements.

* { 
  box-sizing: border-box; 
}

### **Liquid Layouts:**
Uses relative percentage (`%`) units so elements stretch and compress relative to the screen or parent window size.
  **max-width:** The maximum pixel width an element can stretch, regardless of how large the window gets.
  **min-width:** The minimum pixel width an element can compress, regardless of how small the window gets.

### **Overflow & Scrollbars:**
Used to control content that exceeds the size of its container box.
  **overflow: auto;** : Scrollbar appears only when text overflows.
  **Requirement:** The height of the box must be set for `auto` to work.
  **Other options:** `visible` (default), `scroll` (always shows scrollbar), `hidden` (clips the overflow).

### **Custom Fonts (@import):**
Used to download a specific font family into the user's browser.
  **Import Syntax:** `@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap');`
  **Application:** `font-family: 'Poppins', sans-serif;`

### **Font Units & Ancestry:**
Determines how font sizes change when elements are nested.
  **px:** Exact, fixed pixel size for specific text.
  **em:** Relative to the parent element's size (multiplies as you nest deeper).
  **rem:** Relative to the root `<html>` element size (consistent, ignores nesting).

### **Shadows (Box & Text):**
  **Point to remember:** A shadow becomes completely solid with hard edges when Blur = 0px.
  **Box Shadow Syntax:** `box-shadow: [X] [Y] [Blur] [Spread] [Color] [inset];`
  **Text Shadow Syntax:** `text-shadow: [X] [Y] [Blur] [Color];`
  **Positioning Details:**
    **X (Horizontal):** Positive = moves shadow right. Negative = moves shadow left.
    **Y (Vertical):** Positive = moves shadow down. Negative = moves shadow up.
  **Coloring:** Always use `rgba(red, green, blue, alpha)` to control shadow opacity.

### **CSS Variables:**
  **Declaration Syntax:** Always starts with two dashes `--`.
    **Example:** `--main-color: blue;`
  **Calling the Variable:** Use the `var()` function.
    **Example:** `color: var(--main-color);`
  **Global Variables:** Declared inside the `:root` pseudo-class (which represents the HTML tag) so they can be accessed anywhere.

:root { 
  --main-color: blue; 
}































