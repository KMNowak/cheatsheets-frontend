#css-grid

Cheatsheet for `css-grid`.
## grid-gap
- defines space between grid elements
- it's  a shorthand for `grid-row-gap` and `grid-column-gap`
```css
.gapped {
  /* 10px for rows, 300px for columns */
  grid-gap: 10px 300px;
}
```

## grid-template-areas
- `grid-template-areas` property defines how `grid-area`-named elements aligns
- very clear, obvious way - what in css that is on a page
- **overrides html order**

[Example](grid-template-areas/index.html)
## grid-template-columns & grid-template-rows
- defines exactly how columns/rows are spreading
- `auto` value - then columns/rows spread evenly
- `XXXpx` value - then the given column/row is exactly of this size
- `XXXfr` value - then gives column/row automatic, XXX proportions according to others e.g:
```css
.container {
  /* middle column is 3 times wider than neighbours */
  /* all fr columns take all available space */
  grid-template-columns: 1fr 3fr 1fr;
}
```

[Example `.container`](grid-column_and_grid-row_manipulations/styles.css)

## grid-column-start & grid-row-start
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
  grid-column: 3 / span -1; /* -1 means span to the end of the column*/
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

## Named grid-template-rows and grid-template-columns

- named template for more declarative styling
- assign given name to particular class with props `grid-column` and `grid-row`.

```css
.container {
  grid-template-columns: 
    [custom-column-name-1] 1fr /* 1fr can be replaced by any value you want */
    [custom-column-name-2] 1fr ;
  grid-template-rows: 
    [custom-row-name-1] 100%;
}

.with-custom { /* assignment */
  grid-column: custom-column-name-1; 
  grid-row: custom-row-name-1;
}
```

**⚠ Be careful with using % value in pair with** `grid-gap` since it can cause overflow. It's safer to use `fr`.

[Example `.container`](grid-template_named/styles.css)

