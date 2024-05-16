---
tags:
  - WebDev
---
*Goes over the HTML and CSS file, explaining what everything does*

[Display Grid - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/display#grid)
* This element behaves like a block-level element and lays out its content according to the grid model.
	* Example: `display: grid;`

[Grid-Auto-Flow - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow)
* This property controls how the auto-placement algorithm works, specifying exactly how auto-placed items get flowed into the grid.
	* Example: `grid-auto-flow: row;`

[Grid-Template-Columns - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
* This property defines the line names and track sizing functions of the grid columns.
	* Example: `grid-template-columns: 1fr 60px;`

[Grid-Template-Rows - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
* This property defines the line names and track sizing functions of the grid rows.
	* Example: `grid-template-rows: 1fr 2fr 1fr;`

[Grid-Auto-Rows - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows)
* This property specifies the size of an implicitly-created grid row track or pattern of tracks.
	* Example: `grid-auto-rows: minmax(30px, auto);`

[Grid-Auto-Columns - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns)
* This property specifies the size of an implicitly-created grid column track or pattern of tracks.
	* Example: `grid-auto-columns: 1fr;`

[Row Gap - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap)
* This property sets the size of the gap (gutter) between an element's rows.
	* Example: `row-gap: 1em;`

[Column Gap - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap)
* This property sets the size of the gap (gutter) between an element's columns.
	* Example: `column-gap: 20px;`

[Grid-Column-Start - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-start)
* This property specifies a grid item's start position within the grid column by contributing a line, a span, or nothing (automatic) to its grid placement. This start position defines the block-start edge of the grid area.
	* Example: `grid-column-start: -1;`

[Grid-Column-End - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-end)
* This property specifies a grid item's end position within the grid column by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the block-end edge of its grid area.
	* Example: `grid-column-end: 3;`

[Grid-Row-Start - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start)
* This property specifies a grid item's start position within the grid row by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the inline-start edge of its grid area.
	* Example: `grid-row-start: 2;`

[Grid-Row-End - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end)
* This property specifies a grid item's end position within the grid row by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the inline-end edge of its grid area.
	* Example: `grid-row-end: 3;`

[Grid-Column Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column)
* This shorthand property specifies a grid item's size and location within a grid column by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the inline-start and inline-end edge of its grid area.
	* Example: `grid-column: 2 / 4;`

[Grid-Row Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row)
* This shorthand property specifies a grid item's size and location within a grid row by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the inline-start and inline-end edge of its grid area.
	* Example: `grid-row: 2 / -1;`

[Place-Content Shorthand - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/place-content)
* This shorthand property allows you to align content along both the block and inline directions at once (i.e. the `align-content` and `justify-content` properties) in a relevant layout system such as Grid or Flexbox.
	* Example: `place-content: end center;`

[Grid-Template-Areas - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
* This property specifies named grid areas, establishing the cells in the grid and assigning them names.
* *Refer to Lesson 15 index and CSS files in the Dave Gray folder*

[Grid-Area - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area)
* This shorthand property specifies a grid item's size and location within a grid by contributing a line, a span, or nothing (automatic) to its grid placement, thereby specifying the edges of its grid area.
	* Example: `grid-area: 2 / 1 / 2 / 4;`

Best way to practice CSS Grids is by playing [Grid Garden](https://cssgridgarden.com/)
* 28 different levels/challenge to master CSS Grid and learn a lot more about the grid system.