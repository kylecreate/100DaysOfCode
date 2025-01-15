---
tags:
  - learning-notes
  - code-for-dummies-book-2
  - CSS
obsidianUIMode: preview
---
> I'm controlling, and I want everything orderly, and I need lists.
> — Sandra Bullock

Lists and tables make things easier for you to understand at a glance.
In this chapter, you find out how to use lists, tables, and forms, and how to know when these elements are appropriate for your content.

## Organizing Content on the Page
- Readability is the most important principle for organizing and displaying content on your web page.
    - Pages should allow visitors to easily read, understand, and act on your content.
    - Reviewing figures 2-1 and 2-2 (on page 64 and 65) you can see the differences in a structured list example from Craigslist and Kayak.com.
        - Craigslist's list is a little jagged and weird
        - Kayak.com's list is nicely centered and easily read

TIP: Don’t underestimate the power of simplicity when displaying content.
Before displaying content on a webpage, ask yourself a few questions.
  1. Does your content have one attribute with related data, or does it follow sequential steps?
      - *Consider using a list*
  2. Does your content have multiple attributes suitable for comparision?
      - *Also consider using a list*
  3. Do you need to collect input from the visitor?
      - *Consider using forms*
Pick one of these options and see how the visitors react when viewing your website.
## Listing Data
Websites have used lists for decades to convey related or hierarchical information.
- Viewing an example of Yahoo's website from 1997 which uses bulleted lists to display various categories and a Food.com recipe that uses list to display the ingredients in the recipe.
### Creating ordered and unordered lists
There's 2 popular types of lists used in HTML
1. **Ordered**: These lists are numerical or alphabetical lists in which sequence of list items is important.
2. **Unordered**: These lists are usually bulleted lists in which the sequence of the list has no importance.

You create lists by specifying the type of list as ordered or unordered and then adding each list item using the `li` tag.
1. Specify the type of list
    - Adding an opening and closing list tag that specifies either an ordered or unordered list.
    - `ol` to specify the beginning and end of the ordered list
    - `ul` to specify the beginner and end of the unordered list
2. Add an opening and closing tag for each item in the list using the `li` tag.
```HTML fold
<ol>
	<li> List Item #1 </li>
	<li> List Item #2 </li>
	<li> List Item #3 </li>
</ol>
```

### Nesting lists
You can nest a list inside a list, and either type of list can be nested inside of another list. Just replace one of the list item tags with a list type tag.
```HTML fold
<ul>
	<li> Send sketches to London office </li>
	<li> File expenses report </li>
	<ol>
		<li> Trip to San Francisco </li>
		<li> Trip to Los Angeles </li>
	</ol>
</li>
```

## Putting Data in Tables
Tables help further organize text and tabular data on the page.
Tables act as containers and can hold and display any type of content, including text, such as heading and lists and images.
TIP: Avoid using tables to create page layouts
### Basic table structure
1. You create a table with the `table` element.
    - Using the `<table> </table>` tags
2. Divide the table into rows with the `tr` element
    - *Between the opening and closing table tags, create opening tags and closing tags for each row of your table.*
3. Divide rows into cells using the `td` element
    - Between the opening and closing `tr` tags, create opening and closing `td` tags for each cell in the row.
4. Highlight cells that are headers using the `th` element
    - Finally, specify any cells that are headers by replacing the `td` element with a `th` element.

REMEMBER: The table will only have one opening and closing table tag, but you can have more than one row and cell in the table.
```HTML fold
<table>
	<tr>
		<th>Table Header #1</th>
		<th>Table Header #2</th>
	</tr>
	<tr>
		<td>Row #1, Cell #1</td>
		<td>Row #1, Cell #2</td>
	</tr>
	<tr>
		<td>Row #2, Cell #1</td>
		<td>Row #2, Cell #2</td>
	</tr>
</table>
```

### Stretching table columns and rows
Stretching a cell across columns or rows is called *spanning*.
- The `colspan` attribute spans a column over subsequent vertical columns.
    - The value of the `colspan` attribute is set equal to the number of columns you want to span. You always span a column from left to right
- The `rowspan` attribute spans a row over subsequent horizontal rows.
    - Set `rowspan` equal to the number of rows you want to span.

The following code generates a part of the table shown in Figure 2-8 *(on page 71).*
```HTML fold
<tr>
	<td colspan="2">
		<strong>Total Revenue</strong>
	</td>
	<td>
		<strong>112,330,000</strong>
	</td>
	<td>
		<strong>85,965,000</strong>
	</td>
	<td>
		<strong>70,697,000</strong>
	</td>
	<td>
		<strong>55,838,000</strong>
	</td>
</tr>
```

### Aligning tables and cells
- The latest version of HTML does not support the tags and attributes in this section.
    - There is no guarantee your browser will correctly render it in the future.

The `table` element has three depercated attributes…
Table Attributes Replaced by CSS

| **Attribute Name** | **Possible Values** |                                                                                                                                                                    **Description** |
|:-------------------|:--------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              align | left, center, right | Position of table relative to the containing document according to the value of the attribute. For example, `align="right"` positions the table on the right side of the web page. |
|              width |       pixels (#), % |                                                                      Width of table measured either in pixels on-screen or as a percentage of the browser window or container tag. |
|             border |          pixels (#) |                                                                                                                                                   Width of table border in pixels. |

The example code below shows the syntax for creating the table shown in figure 2-9 *(page 73)*
```HTML fold
<table align="right" width=50% border=1>
	<tr>
		<td>The Social Network</td>
		<td>Generation Like</td>
	</tr>
	<tr>
		<td>Tron</td>
		<td>War Games</td>
	</tr>
</table>
```

The `tr` element has two deprecated attributes, `align` and `valign`
Table Row Attributes Replaced by CSS

| **Attribute Name** |          **Possible Values** |                                                                                                                                                                        **Description** |
|:-------------------|:-----------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              align | left, right, center, justify |     Horizontal alignment of a row’s cell contents according to the value of the attribute. For example, `align="right"` positions a row’s cell contents on the right side of each cell |
|             valign |          top, middle, bottom |           Vertical alignment of a row’s cell contents according to the value of the attribute. For example, align="bottom" positions a row’s cell contents on the bottom of each cell. |

The `td` element has four deprecated attributes
Table Cell Attributes Replaced by CSS

| **Attribute Name** |          **Possible Values** |                                                                                                                                                                        **Description** |
|:-------------------|:-----------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              align | left, right, center, justify |     Horizontal alignment of a row’s cell contents according to the value of the attribute. For example, `align="right"` positions a row’s cell contents on the right side of each cell |
|             valign |          top, middle, bottom |           Vertical alignment of a row’s cell contents according to the value of the attribute. For example, align="bottom" positions a row’s cell contents on the bottom of each cell. |
|              width |                 pixels (#) % |                                                                                             Width of a cell measured either in pixels on-screen or as a percentage of the table width. |
|             height |                 pixels (#) % |                                                                                            Height of a cell measured either in pixels on-screen or as a percentage of the table width. |

The example code below shows the syntax for creating the table featured in figure 2-10 *(page 75)*
```HTML fold
<table align="right" width=50% border=1>
	<tr align="right" valign="bottom">
		<td height=100>The Social Network</td>
		<td>Generation Like</td>
	</tr>
	<tr>
		<td height=200 align="center" valign="middle">Tron</td>
		<td align="center" valign="top" width=20%>War Games</td>
	</tr>
</table>
```

REMEMBER: These attributes are no longer support and they should never be used.
## Filling Out Forms
Forms allow you to capture input from your website visitors.
Capturing input from visitors allows you to…
1. **Modify existing content on the page.** For example, price and date filters on an airline website allows the user to find a desiered flight more quickly.
2. **Store the input for later use**. For example, a website may use a registration form to collect your email, username, and password information to allow you to access it at a later date.

### Understanding how forms work
Forms pass info entered by a user to a server by using this process…
1. The browser displays a form on the client's machine.
2. The user completes the form and presses a submit button.
3. The browser then submits the data collected from the form to a server
4. The server then processes and stores the data and sends a response to the client's machine.
5. The browser displays the response, usually indicating whether the submission was successful or not.

REMEMBER: Step 3-5 are beyond the scope of the book, no need to worry about this right now.
- Forms are very flexible and can record a variety of user inputs.
    - Input fields used in forms can include free text fields, radio buttons, checkboxes, drop-down menus, range sliders, dates, phone numbers, and more.

Selected Form Attributes

| **Attribute Name** |                                       Possible Values |                                                                                                                                               Description |
|:-------------------|:------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------|
|               type | checkbox, email, submit, text, password, radio, etc.. | Defines the type of input field to display in the form. For example, `text` is used for free text fields, and `submit` is used to create a Submit button. |
|              value |                                                  text |                                                                                                                   The initial value of the input control. |

### Creating a basic form
Follow the steps to create a basic form
1. Define a form with the `form` element
2. Using the `action` attribute, specify the `form` element where to send the form data.
3. Using the `method` attribute, specify in the form element how to send form data.
    - `**POST**` is used for storing sensitive information *(such as credit card numbers)*
    - `**GET**` is used to allow users to bookmark or share with others the results of a submitted form *(for example, airline flight listings)*.
4. Provide a way for users to input and submit responses with the `input` element.
5. Specify input types using the `type` attribute in the `input` element
6. Lastly, create another `input` tag and set the `type` attribute equal to `submit` .

Example code from these steps
```HTML fold
<form action="mailto:random@email.com" method="POST">
	<input type="text" value="Type a short message here">
	<input type="submit">
</form>
```
- The action attribute in this form is set equal to mailto, which signals to the browser to send an email using your default mail client.
