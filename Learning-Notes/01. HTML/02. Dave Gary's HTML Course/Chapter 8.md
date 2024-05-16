---
tags:
  - WebDev
---
Adding a table to our webpage
Tables structure tabular data, which is data that is made up up rows and columns
* Mainly seen in a schedule, stats in sports, and many other different types of data
* **Don’t use tables** for an entire page layout which was common to do in the 90’s
* They do need a bit of CSS to look accurate, but it’s not needed.

[Table Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
* This element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.

[TR Element (Table Row) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)
* This element defines a row of cells in a table. The row's cells can then be established using a mix of `<td>` (data cell) and `<th>` (header cell) elements.

[TD Element (Table Data) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)
* This element defines a cell of a table that contains data. It participates in the _table model_.

[TBody Element (Table Body) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)
* This element encapsulates a set of table rows (`<tr>` elements), indicating that they comprise the body of the table (`<table>`).

[TH Element (Table Header) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th)
* This element defines a cell as the header of a group of table cells. The exact nature of this group is defined by the `scope` and `headers` attributes.

[`Rowspan` Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td#rowspan)
* This attribute contains a non-negative integer value that indicates for how many rows the cell extends. Its default value is `1`; if its value is set to `0`, it extends until the end of the table section `<thead>`, `<tbody>`,  and `<tfoot>`, even if implicitly defined), that the cell belongs to.

[THead Element (Table Header) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead)
* This element defines a set of rows defining the head of the columns of the table.

[TFoot Element (Table Footer) - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot)
* This element defines a set of rows summarizing the columns of the table.

[Scope Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th#scope)
* Helping assistive technology
* This attribute defines the cells that the header (defined in the `<th>`) element relates to. It may have the following values…
	* Row: The header relates to all cells of the row it belongs to.
	* `Col`: The header relates to all cells of the column it belongs to.
	* Rowgroup: The header belongs to a rowgroup and relates to all of its cells.
	* Colgroup: The header belongs to a colgroup and relates to all of its cells.