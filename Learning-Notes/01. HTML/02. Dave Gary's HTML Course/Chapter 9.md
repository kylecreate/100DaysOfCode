---
tags:
  - WebDev
---
The HTML that’s been created so far in the past 8 chapters, has been 1-way communicated. Now, we’re going to add and learn about forms which should be able to have users send information back to us.

[Form Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
* This element represents a document section containing interactive controls for submitting information.

[Action Attribute in the Form Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#action)
* The URL that processes the form submission. This value can be overridden by a `formaction` attribute on a `<button>`, `<input type="submit">`, or `<input type="image">` element. This attribute is ignored when `method="dialog"` is set.

[Method Attributes - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#method)
* The HTTP method to submit the form with. The only allowed methods/values are (case insensitive):
	* Post: The `POST` method; form data sent as the request body.
	* Get (default): The `GET`; form data appended to the `action` URL with a `?` separator. Use this method when the form has no side effects.
	* Dialog: When the form is inside a `<dialog>`, closes the dialog and causes a `submit` event to be fired on submission, without submitting data or clearing the form.

[Label Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
* This element represents a caption for an item in a user interface.

[Input Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
* The **`<input>`** HTML element is used to create interactive controls for web-based forms in order to accept data from the user; a wide variety of types of input data and control widgets are available, depending on the device and user agent. The `<input>` element is one of the most powerful and complex in all of HTML due to the sheer number of combinations of input types and attributes.

[Pattern Attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)
* This attribute specifies a regular expression the form control's value should match. If a non-`null` value doesn't conform to the constraints set by the `pattern` value, the `ValidityState` object's read-only `patternMismatch` property will be true.

[Select Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
* This element represents a control that provides a menu of options.

[Datalist Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist)
* This element contains a set of `<option>` elements that represent the permissible or recommended options available to choose from within other controls.

[Fieldset Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)
* This element is used to group several controls as well as labels (`<label>`) within a web form.

[Legend Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend)
* This element represents a caption for the content of its parent `<fieldset>`.

[Radio Button Input - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)
* The elements of type `radio` are generally used in **radio groups**—collections of radio buttons describing a set of related options.

[Checkbox Input - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)
* The elements of type `checkbox` are rendered by default as boxes that are checked (ticked) when activated, like you might see in an official government paper form.

[Textarea Input - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text)
* The elements of type `text` create basic single-line text fields.

[Button Element - MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
* This element is an interactive element activated by a user with a mouse, keyboard, finger, voice command, or other assistive technology. Once activated, it then performs an action, such as submitting a form or opening a dialog.

After submitting the form and inputting all the required boxes, it takes us to the httpbin website with a bunch of code.
* This shows us all the information that would be sent with the form from the user.
* The headers section is the server information, which we’re not concerned about.