---
tags:
  - WebDev
---
Going to be learning how to add images to our webpage.
It is common for you to have your images in a separate folder (IE: imgs or images) while working on a project. It’s good to be organized when creating one.

[Image Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
* *Self closing tag element*
* The `src` attribute tells HTML where to grab the image that we want to use.
* The `alt` attribute serves a couple of purposes…
	1. To help assistive technology for those that aren’t able to see the image which will read the description of the image. If the image is broken in any way, the text will he shown instead of the image.
* The `title` attribute is not accessible to screen readers but the image is complete without it. This will popup a box with text. This was required in the 90’s, but not so much now.
* The `width` and `height` attribute will change the size of the image to whatever is set by the person coding it.  These attributes are coming back and can be useful.
	* The reason it’s now recommended and making a comeback is to use this even though we can use CSS is because of <u>cumulative layout shift</u> and to tell the browser how much space the image will be taking up instead of it being unknown.
		* Cumulative Layout Shift - A measure of how much a webpage unexpectedly shifts during its life

[Loading attribute for images - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attributes)
* Indicates how the browser should load the image
	* <u>Eager</u>: Loads the image immediately, regardless of whether or not the image is currently within the visible viewport *(this is the default value)*.
	* <u>Lazy</u>: Defers loading the image until it reaches a calculated distance from the viewport, as defined by the browser. The intent is to avoid the network and storage bandwidth needed to handle the image until it's reasonably certain that it will be needed. This generally improves the performance of the content in most typical use cases.

```HTML file:image-examples fold
<img src="img/caribbean.jpg" alt="Caribbean Beach" title="I want to visit a Caribbean beach." width="400" height="225" loading="lazy">

<img src="img/html_logo_300x300.png" alt="HTML5 Logo" title="I am learning HTML5" width="300" height="300">
```

[Figure Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
* Not just for images
* Can also contain a code sample, refer to that below
	* This element represents self-contained content, potentially with an optional caption, which is specified using the `<figcaption>` element. The figure, its caption, and its contents are referenced as a single unit.

[Figure Caption Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption)
* Not just for images
* Needs to either be the first thing inside of a figure or the last thing. Either or
	* This element represents a caption or legend describing the rest of the contents of its parent `<figure>` element.

[Code Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code)
* This element displays its contents styled in a fashion intended to indicate that the text is a short fragment of computer code. By default, the content text is displayed using the user agent's default monospace font.

```HTML file:figure-examples-with-code-example fold
<figure>
	<img src="img/vacation.jpg" alt="Cancun Vacation" title="It's 5 o'Clock Somewhere!" width="400" height="267" loading="lazy">
	<figcaption>
		A Caribbean Vacation Image
	</figcaption>
</figure>

<figure>
	<figcaption>An example of HTML5 Code</figcaption>
		<p>
			<code>
				&lt;h1&gt;Hello World!&lt;/h1&gt;
			</code>
		</p>
</figure>
```

### <u>Resources</u>
* [Placeholder Images](https://loremipsum.io/21-of-the-best-placeholder-image-generators/) - Random image generator with random sizes
* [Unsplash](https://unsplash.com/) - Free use images
* [Pexels](https://www.pexels.com/) - Free use images
* [Pixabay](https://pixabay.com/) - Free use images
* [TinyPNG](https://tinypng.com/) - Compressing images into other file formats