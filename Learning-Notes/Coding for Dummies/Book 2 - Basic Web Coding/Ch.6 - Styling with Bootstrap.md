---
tags:
  - learning-notes
  - code-for-dummies-book-2
  - CSS
obsidianUIMode: preview
---
> "None of us got where are are solely by pulling ourselves up by out bootstraps. We got here because somebody -- a parent, a teacher, an Ivy League crony, or a few nuns -- bent down and helped us pick up our boots."
>  -- Thurgood Marshal

Bootstrap is a free toolkit that allows users to create webpages quickly. Developed back in 2011 by two Twitter developers (Mark Otto and Jacob Thornton), it was originally created for internal use at Twitter before being released to the public.

Before Bootstrap was released, developers would create common webpage features (IE: navigation bars, grids, etc.) over and over again which took time to spend on maintaining those features. With this tool, it's become one of the most popular for creating websites.

As long as you have a basic understanding of HTML and CSS, you can use and customize it to whatever you want for your own projects.

---
## Figuring Out What Bootstrap Does
Using a website like The Washington Post, the webpage should look like a newspaper while viewing it on a Desktop browser. The page will use the same font size and typeface for the main headlines, captions, and bylines. Because newspapers follow a defined format to begin with, it would be good to style this ahead of time with different class names written in your CSS file and then refer back to it when creating the format of the page.

This is how Bootstrap functions at it's core. It's a collection of prewritten HTML, CSS, and JavaScript that you can use referenced class names and then further customize it yourself. Bootstrap CSS allows you to create and gives the following.
	**Layouts**: Define your webpage content and elements in a grid pattern.
	**Components**: Use existing buttons, menus, and icons that have been tested on hundreds of users.
	**Responsiveness**: A fancy word for whether the site your creating will work on mobile or tablet views in addition to desktop views. With CSS, you'd create code that would appear differently on different screen sizes. But with Bootstrap, it's already done for you.
	**Cross-browser Compatibility**: Chrome, Firefox, Safari, Edge, and others can all vary in the way they render out certain HTML and CSS elements/properties. Bootstrap is optimized so the webpages being created appear the same across all browsers.

---
## Installing Bootstrap
To install Bootstrap to your HTML file, do the following steps...
1. Open your web browser and go to the [Bootstrap official website](https://getbootstrap.com/).
2. Click on the download button to go to the download page
3. Scroll down on that page using the navigation link on the right side to find the section called `CDN via jsDelivr` or click [this link](https://getbootstrap.com/docs/5.3/getting-started/download/#cdn-via-jsdelivr)
4. Click on the first copy button of the `CDM via jsDelivr` section to copy the code to include Bootstrap in your webpage.
5. Paste the code copied from that page to your HTML file between the opening and closing of the `<head></head>` tags.

<strong><span style="color:yellow">TIP 💡</span></strong>: The `<link>` and `<script>` tags download Bootstrap from a <u>CDN</u> (Content Delivery Network) which is a network that's serving code and media files to users no matter where they're located.
<strong><span style="color:yellow">TIP 💡</span></strong>: If you'd like to try Bootstrap CSS using Codesandbox.io or another code sandbox, you can create a new project with a static template and paste in the CDN links inside the head tags. After you save the page, the file should have bootstrap styles applied to it.

---
## Understanding the Layout Options
Bootstrap CSS allows you to layout content quickly and easily using the grid system. You have three options when using this system...
1. **Code Yourself**: After you learn how the grid is organized, you can write code to create any type of layout you want.
2. **Code with a Bootstrap editor**: Instead of writing the code in a text editor, you can drag and drop elements to generate bootstrap code. After that, you can download and use the code yourself.
3. **Code with a prebuilt theme**: Download a free or paid Bootstrap theme where the website has already been created and you fill in your own content.

### Lining up on the grid system
Bootstrap divides the screen into a grid system of 12 equally sized columns. There's a few rules to follow...
1. **Columns must sum to a width of 12 columns**: You can use 1 column that is 12 columns wide or 12 columns that are one column wide or anything in-between.
2. **Columns can contain content or spaces**: You could have a 4-column-wide column, a space of 4 columns, and another 4-column-wide column.
*Note: Unless you specify otherwise, the columns will automatically stack into a single column on a smaller browser size or screen and then expand horizontally on a larger screen size.*

To create any layout, follow these steps...
1. Create a `<div>` tag with the attribute `class="container"`.
2. Inside that first `<div>` tag, create another `<div>` inside of that with the attribute `class="row"`.
3. For each row created, create another `<div>` tag with the attribute `class="col-md-X"`. Set *X* equal to the number of columns the row should span.

<strong><span style="color:yellow">WARNING ❗</span></strong>: You must include `<div class="container">` at the beginning of your page and have a closing `</div>` tag at the end of the page or the page won't render out completely.

The following code creates a simple three-column-centered layout...
* To view a live example, check out [Zoom's website](https://www.zoom.com) and resize the page for different sizes to show the difference.
* The lorem ipsum text is commonly used to create filler text that doesn't mean anything. It originates from a first-century BC Latin text by Cicero.
```HTML file:three-column-layout-bootstrap fold
<div class="container">

	<!-- EXAMPLE ROW OF COLUMNS -->
	<div class="row">
		<div class="col-md-4">
			<h2>Heading</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non suscipit felis. Curabitur volutpat pulvinar.</p>
		</div>
		<div class="col-md-4">
			<h2>Heading</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non suscipit felis. Curabitur volutpat pulvinar.</p>
		</div>
		<div class="col-md-4">
			<h2>Heading</h2>
			<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc non suscipit felis. Curabitur volutpat pulvinar.</p>
		</div>
	</div>
</div>
```

### Dragging and dropping to a website
After taking a look at the code mentioned above, there are easier ways to generate the code without having to type it out yourself. Different Bootstrap CSS editors allow you to drag and drop components to create a layout which will generate the code for you.
* [Layoutit.com](https://build.layoutit.com/): Free Bootstrap editor that allows you to drag and drop components and then download the source code for yourself.
* [Pingendo.com](https://pingendo.com/): Free downloadable drag-and-drop Bootstrap CSS editor.
* [Codeply.com](https://www.codeply.com/): Free online code editor with built-in support for Bootstrap CSS.
<strong><span style="color:yellow">TIP 💡</span></strong>: These sites are free and can stop working at any time without a notice. There's similar and more websites like these by searching *Bootstrap CSS editors* on Google.

### Using predefined templates
There are sites that exist with ready-to-use Bootstrap themes that can be downloaded or free or purchased.
* [bootstrapzero.com](https://www.bootstrapzero.com/): A collection of free, open-source Bootstrap CSS templates
* [bootswatch.com](https://bootswatch.com/) & [bootsnipp.com](https://bootsnipp.com/):  These include prebuilt Bootstrap CSS components that you can use to assemble your own website.
* [wrapbootstrap.com](https://wrapbootstrap.com/): Bootstrap CSS templates that you can purchase.
<strong><span style="color:yellow">TIP 💡</span></strong>: Bootstrap CSS themes that are free but also may require attribution to the author, email registration, or a automated tweet to download/use.

### Adapting layout for mobile, tablet, and desktop
The Bootstrap grid is made for mobile first use. If you want to have multiple columns on larger devices, you can use `col-xx-xx` classes. Bootstrap uses a different class prefix to target each breakpoint except the extra small one, which is defaulted.

|                | Extra Small<br>(<576px) | Small<br>(>=576px) | Medium<br>(>=768px) | Large<br>(>=992px) | Extra Large<br>(>=1200px) | Extra Extra Large<br>(>=1400px) |
| -------------- | ----------------------- | ------------------ | ------------------- | ------------------ | ------------------------- | ------------------------------- |
| Class Prefix   | `col-xs-`               | `col-sm-`          | `col-md-`           | `col-lg-`          | `col-xl-`                 | `col-xxl-`                      |
| Example device | Phones                  | Tablets            | Laptops             | Desktops           | Large screens             | Extra large screens, TVs        |
<strong><span style="color:yellow">REMEMBER 👍🏼</span></strong>: Since Bootstrap CSS is mobile first, you only need to use the `col-xs-` breakpoint if you want to divide  a mobile screen into multiple columns. To display a layout in a single column on a small screen, then you don't need to do `col-xs-12`.

A website with two equally sized columns on tablets, desktops, large desktops, and TVs should use `col-sm-` class name.
* For Desktop and larger devices, then you should add `col-md-`.
* For even larger screens and TVs, then you should add `col-lg-`.
```HTML file:example-of-col-sm-2 fold
<div class="container">
	<div class="row">
		<div class="col-sm-6 col-md-4 col-lg-2">Column 1</div>
		<div class="col-sm-6 col-md-8 col-lg-10">Column 2</div>
	</div>
</div>
```

---
## Coding Basic Web Page Elements
Bootstrap can also create web page components in addition to responsive layouts that can be found on almost every website. Instead of recreating the wheel every time by making multiple buttons or toolbars, you can use pre-built code that's been tested across different devices and users.

### Designing Buttons
Buttons are a basic element that are created on web pages which can be sometimes difficult to setup and style. The table below is Bootstrap's various types and sizes of buttons.

| Attribute   | Class Prefix                                                                                                             | Description                                                                                                                                                                                                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Button type | `btn-primary`<br>`btn-secondary`<br>`btn-success`<br>`btn-danger btn-warning`<br>`btn-info`<br>`btn-light`<br>`btn-dark` | Blue button with hover effect<br>Gray button with hover effect<br>Green button with hover effect<br>Red button with hover effect<br>Yellow button with hover effect<br>Light blue button with hover effect<br>Light gray button with hover effect<br>Black button with hover effect |
| Button size | `btn-lg btn-sm`                                                                                                          | Large button size<br>Default button size<br>Small button size                                                                                                                                                                                                                       |
To view the different button types within Bootstrap CSS, write the following HTML code.
```HTML file:buttons-in-bootstrap fold
<p>
	<button type="button" class="btn btn-primary btn-lg">Large primary button</button>
	<button type="button" class="btn btn-danger btn-lg">Large danger button</button>
</p>

<p>
	<button type="button" class="btn btn-success">Default success button</button>
	<button type="button" class="btn btn-info">Default info button</button>
</p>

<p>
	<button type="button" class="btn btn-warning btn-sm">Small warning button</button>
	<button type="button" class="btn btn-dark btn-sm">Small dark button</button>
</p>
```

<strong><span style="color:yellow">TIP 💡</span></strong>: For additional button types, sizes, and other options, check out the [documentation](https://getbootstrap.com/docs/4.0/components/buttons/).

### Navigating with toolbars
Web pages with multiple pages or views usually have one or more toolbars to help with navigation.

| Attribute           | Class Prefix                        | Description                                                                              |
| ------------------- | ----------------------------------- | ---------------------------------------------------------------------------------------- |
| Toolbar Type        | `nav-tabs`<br>`nav-pills`           | Tabbed navigation toolbar<br>Pill, or solid button navigation toolbar                    |
| Toolbar Button Type | `dropdown`<br>`caret dropdown-menu` | Button or tab as dropdown menu<br>Drop-arrow drop-down menu icon<br>Drop-down menu items |
To create a pill or solid button navigation toolbar, you can write the following...
```HTML file:bootstrap-responsive-toolbar fold
<ul class="nav nav-pills">
	<li class="nav-item">
		<a class="nav-link active" href="#">Link 1</a>
	</li>
	<li class="nav-item">
		<a class="nav-link active" href="#">Link 2</a>
	</li>
	<li class="nav-item">
		<a class="nav-link active" href="#">Link 3</a>
	</li>
	<li class="nav-item">
		<a class="nav-link active" href="#">Link 4</a>
	</li>
	<li class="nav-item dropdown">
		<a class="nav-link downdown-toggle" data-bs-toggle="dropdown" href="#">More
			<span class="caret"></span>
		</a>
		<ul class="dropdown-menu">
			<li class="nav-item">
				<a class="nav-link" href="#">Item 1</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Item 2</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Item 3</a>
			</li>
		</ul>
	</li>
</ul>
```

<strong><span style="color:yellow">TIP 💡</span></strong>: The `dropdown-toggle` class and the `data-bs-toggle="dropdown"` attribute and value work together to add drop-down menu elements such as links using Bootstrap.

### Adding Icons
Icons are used frequently with buttons to help convey some type of action (like an email icon or trash can icon) which suggests to users a simple explanation of what it is/does.
* They're free to use and open-source
* There's more than 1,500+ icons in the library that are free to use.
* Need to use a CDN URL to use the icons that is placed within the `<head></head>` tags.
```HTML file:bootstrap-icons-examples fold
<button type="button" class="btn btn-light">Star
	<i class="bi bi-star"></i>
</button>

<button type="button" class="btn btn-light">Attach
	<i class="bi bi-papreclip"></i>
</button>

<button type="button" class="btn btn-light">Trash
	<i class="bi bi-trash"></i>
</button>
```