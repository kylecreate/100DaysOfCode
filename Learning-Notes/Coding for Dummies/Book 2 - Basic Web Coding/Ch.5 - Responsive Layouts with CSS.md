---
tags:
  - ReadingNotes
  - WebDev
---
> “The measure of intelligence is the ability to change.”
> — Albert Einstein

With this chapter, you continue building on the knowledge of CSS you gained in the previous chapters of book 2.

**TIP**: Flexbox can be confusing at first, until you do some hands-on work with it. Practice in a sandbox for a while until you understand it and how it works.

## Introducing Responsive Design
- *Responsive design* is the practice of making web pages and web apps that adjust to fit the width of the browser window in which they appear.
### The web is mobile
- In 2016, the number of web pages viewed on mobile devices surpassed
the number of web pages viewed on desktop (including laptop) devices globally.
- Today, around two-thirds of all web page views come from mobile devices.

### Why are so many sites mobile-unfriendly?
- There is an inherent bias in web development toward desktop browsers than mobile browsers.
    - Most web developers will treat websites on mobile as a second thought rather than their first thought.

**WARNING**: A website built without taking mobile browsers into consideration from the very beginning is likely to not work as well on mobile devices as it does on desktop, or to not be usable at all on mobile.
### Introducing mobile-first design
- In "mobile-first design", instead of making a web page that works for desktop devices and then scaling it down for mobile devices, we design web pages first for mobile and then scale them up for desktop devices.
### Making responsive web pages with the viewport meta tag
- A `viewport` meta tag is an instruction for the web browser that tells it how to scale the virtual window in which web pages display, which is called the *viewport*.
    - The reason the web page looks so small on a mobile device is that mobile devices display more pixels per inch than desktop devices.
- The `viewport` meta tag you can use to make a simple web page display correctly on mobile devices.
- [Understanding the Viewport Meta Tag](https://www.youtube.com/watch?v=XrMTuTzX4co) - *YouTube*
```HTML fold
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## Using Flexbox
- By default, web browsers display the elements in an HTML document from left to right and from top to bottom.
    - This is called *normal flow*
- Using CSS `float` and `position` properties, you can modify the normal flow of HTML or even remove elements from the "normal flow" of a document and position them wherever you want.
    - This can be tricky when you're trying to align elements to create a responsive layout.
- A problem with normal flow is that not all languages are written from left
to right.
    - IE: Arabic vs. English
- Flexbox was created to fix the many issues with web page layout using older CSS properties. Some things to know are…
    - All Flexbox layout happens in Flexbox containers (also known as *boxes*).
    - Flexbox is **one-dimensional**. When you work with Flexbox, you only deal with the x axis (rows) or the y axis (columns) at any one time.
    - Flexbox doesn’t assume that the text direction (also known as the *writing mode*) is left-to-right.
    - Flexbox containers and the items inside them are flexible.
### Creating boxes
- Before getting started, you first need to define what part or parts of your web page will use it.
    - You can do this by setting the `display` property to `flex`.
- By default, a container will flow elements inside it horizontally.
- Just as a cardboard box doesn’t make a lot of sense for holding just one thing. You can put several items in that *box* to see what more you can do with it.

Example code of creating three div elements in the flex container and giving them a style.
```HTML fold
<head>
	<style>
		#gallery {
			display: flex;
		}

		.box {
			border: 4px solid black;
			margin: 10px;
			width: 100px;
			height: 100px;
			font-size: 36px;
		}
	</style>
</head>
<body>
	<div id="gallery">
		<div class="box">1</div>
		<div class="box">2</div>
		<div class="box">3</div>
		<!-- Multi-line Containers (Read below) -->
		<div class="box">4</div>
		<div class="box">5</div>
		<div class="box">6</div>
	</div>
</body>
```
### Thinking in one dimension
- With flexbox being one dimensional, it means that flexbox only deals with either layout in rows or layout in columns.
- The property to change the dimension that a container flows its items in is `flex-direction`. There's 4 possible values…
    1. row (*the default*)
    2. row-reverse
    3. column
    4. column-reverse
- The following CSS changes the direction of the layout to `column` to make them vertically stacked boxes.
```CSS fold
#gallery {
	display: flex;
	flex-direction: column; /* In order */
}

.box {
	border: 4px solid black;
	margin: 10px;
	width: 100px;
	height: 100px;
	font-size: 36px;
}
```
- You can reverse the order of the items in the box using the `-reverse` values, such as…

```CSS fold
#gallery {
	display: flex;
	flex-direction: row-reverse; /* Reverse Order */
}

.box {
	border: 4px solid black;
	margin: 10px;
	width: 100px;
	height: 100px;
	font-size: 36px;
}
```
### Using multi-line containers
- By default, the items in a flex container will all be on one line.
- You can make the container a multi-line container by using the `flex-wrap`  property.
- With the example code, the `flex-wrap`  property is set to `wrap` which will cause another line to be created when the previous line is filled up with items.
```CSS fold
#gallery {
	display: flex;
	flex-wrap: wrap; /* Multi-line container */
}

.box {
	border: 4px solid black;
	margin: 10px;
	width: 100px;
	height: 100px;
	font-size: 36px;
}
```

**TIP**: Wrapping items in a container is one of the best ways to create a responsive layout with Flexbox. When a multiple-column layout doesn’t fit the width of the viewport, the items that *don’t fit* will just drop down to a new line, rather than going off the page or shrinking down to fit.
### Make no assumptions
- If you’re working in a language with a left-to-right writing mode, your Flexbox containers will flow their items from left to right by default.
- When we talk about the position where a row or column of items begin, we use the term “`start`.”
- When we talk about the position where a row or column of items stops,
we use the term “`end`.”
    - If you use a `-reverse` value for the `flex-direction` property, the items will flow from the end to the start.

### Aligning on the cross-axis
- One of the greatest features of Flexbox is that you can modify the alignment of items on their axis or on their cross-axis.
- You can do this by using the `align-items` property with 4 possible values…
    1. `stretch` - *default value, all items the same size*
    2. `flex-start` - *all items have different heights, same start points*
    3. `flex-end` - *all items end points will align with each other*
    4. `center` - all items will be center vertically if flex-direction is `row` or row `reverse`
### Aligning on the main axis
- To align items on their main axis, use the `justify-content` property. The possible values of this are…
    1. `flex-start` : Items will be justified with the start of the container.
    2. `flex-end` : Items will be justified with the end of the container.
    3. `center` : Items will be centered within the container.
    4. `space-around` : Items are evenly distributed on the line with equal space around each item.
    5. `space-between` : Items are distributed so that the space between them is equal.
    6. `space-evenly` : Items are distributed so that the space between the items and the space to the edges is even.

### Modifying flexible boxes
- All the Flexbox properties mentioned so far are applied to the container, each within the container can also have Flexbox properties applied to it.
    - Example: Modify the sizes or the relative sizes of items within a
Flexbox.
- Three properties that can be applied to affect their size are…
    1. `flex-basis`
        - This property specifies the initial size of an item before the available space in the container is taken into consideration.
        - Default is set to `auto`
        - You can set the property to any other size by specifying a length (*ex. 100px or 80%*).
    2. `flex-grow`
        - This property is a number that indicates what share of the available space an item will get when it’s distributed.
        - Each item in the container has a default value of 1
        - You can have 3 items with equal length, giving the middle item in the container a value of 2 will make it twice as big as the first and third item in the container.
    3. `flex-shrink`
        - This property acts the same as `flex-grow`, but determines how much an item will shrink should there not be enough space for all the items in a container.
        - If the middle item of a 3 item container is given half of the other 2, then it will shrink twice as much.
- Example: You have three items that are each 100 pixels wide, and the container around them is 500 pixels wide, there will be 200 pixels of available space (assuming that the items don’t have margins between them, of course).
### The flex property
- You can specify each property mentioned above individually, it's more common for developers to use shorthand property to set all 3 at the same time.
    - For this, use the `flex` property, which uses the properties in this order.
        - `grow` → `shrink` → `basis`
    - Examples of this being used…
```CSS fold
/* All 3 being used */
flex: 2 1 100px;

/* Using just flex-grow */
flex: 1;

/* Using flex-grow and flex-basis */
flex: 1 100px;
```

**Technical Tip**: There’s no way to use two values to set only `flex-shrink` and `flex-basis`. If that’s what you want to do, you need to use three values and set `flex-grow` as well.
### Changing the order of items
- The order in which items appear in a container will be in the same order in which they appear in the code, by default. You can change the order of items by using the `order`  property.
    - This property takes a number value, which is the order in which the item should appear.
    - By default, all items have a value of 0.
        - *Refer to figure 5-12 on page 140 of an example of this*