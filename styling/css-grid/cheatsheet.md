#css-grid

Cheatsheet for `css-grid`.
## grid-gap
- defines space between grid elements
## grid-template-areas
- `grid-template-areas` property defines how `grid-area`-named elements aligns
- very clear, obvious way - what in css that is on a page
- **overrides html order**
[Example](grid-template-areas/index.html)
## grid-template-columns
- defines exactly how columns are spreading
- can have `auto` value - then columns spread evenly
- can have `XXXpx` value - then the given column is exactly of this size
- can have `XXXfr` value - then gives column automatic, XXX proportions according to others e.g:
```css
.container {
  /* middle column is 3 times wider than neighbours*/
  /* all fr columns take all available space*/
  grid-template-columns: 1fr 3fr 1fr;
}
```
[Example `.container`](grid-column_and_grid-row_manipulations/styles.css)
## grid-column-start
- tells which column/row (counting from 1 left/top side as starting column/row) the column/row starts
- can have value of exact number e.g `4`
- can have value of span e.g. `span 2` which means it starts from default place and spans 2 columns/rows
[Example `.grid-item:nth-of-type(6)`](grid-column_and_grid-row_manipulations/styles.css)
## grid-column-end & grid-row-end
- tells which column the column/row ends (same as `grid-column-start`/`grid-row-start`)
- can have exact value e.g. `3`
- can have value of span e.g. `span 2` which means it automatically ends column/row 2 columns/rows after `grid-column-start`/`grid-row-start`
[Example `.grid-item:nth-of-type(6)`](grid-column_and_grid-row_manipulations/styles.css)
## grid-column
- shorthand for `grid-column-start` & `grid-column-end`
- should be used as in template: `grid-column: start_value / end_value`
- example: 
```css
.grid-item:nth-of-type(6) {
  grid-column: 3 / span 2;
}
```
is equivalent to: 
```css
.grid-item:nth-of-type(6) {
  grid-column-start: 3; 
  grid-column-end: span 2;
}
```
[Example `.grid-item:nth-of-type(6)`](grid-column_and_grid-row_manipulations/styles.css)

## grid-row
- same as [grid-column](##grid-column) but in context of rows
