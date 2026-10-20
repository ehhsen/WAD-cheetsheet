**Flex direction** : .container {flex-direction: row; }
row: left to right (default in the usual left-to-right writing direction).
row-reverse: reverse row order.
column: top to bottom.
column-reverse: bottom to top.
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
 explain of justify content  : flex-start: items at the start.
flex-end: items at the end.
center: items in the center.
space-between: no extra space at the outer edges.
space-around: equal space around each item.
space-evenly: equal space between items and edges.
Wrapping: nowrap: items stay on one line (default).
wrap: items move to another line if necessary.
wrap-reverse: wrapped lines reverse their cross-axis order.
**Flex all properties**: 
**Syntax and Main purpose**
display: flex-> Enables Flexbox
flex-direction ->Sets row or column direction
flex-wrap-> Allows items to wrap
flex-flow ->Shorthand for direction + wrap
justify-content-> Distribution along the main axis
align-items ->Alignment of items within a line
align-content ->Alignment of multiple lines
gap ->Space between items
flex: 1 1 200px ->Grow, shrink, basis
order: 1 ->Changes visual order
align-self-> Overrides alignment for one item
 **grid properties** :
Syntax :Purpose
display: grid-> Enables layout
grid-template-columns: 1fr 1fr ->  Two equal columns
grid-template-rows: 100px auto ->  Defines row sizes
repeat(3, 1fr) ->  Three equal columns
repeat(auto-fit, minmax(200px, 1fr)) ->  Responsive columns
gap: 10px->  Space between rows and columns
grid-column: span 2 -> Item spans two columns
grid-row: span 2->  Item spans two rows
grid-area: header -> Assigns a named area
place-items: center -> Centers items within cells
Grid 


**Key differences**
Flexbox = one dimension.
Grid = two dimensions.
justify-content = main-axis distribution in Flexbox.
align-items = cross-axis alignment in Flexbox.
fr = fraction of available Grid space.
gap = spacing between items/tracks.
@media = responsive layout changes.
