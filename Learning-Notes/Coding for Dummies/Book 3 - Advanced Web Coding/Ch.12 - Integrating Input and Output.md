---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "Malfunction. Need Input."
> -- Number 5, Short Circuit (1986)

Handling user input and sending back results are both basics and necessary functions for any program. With this chapter, you're going to learn how to receive and output data using HTML forms.

## Understanding HTML Forms
The most primary way to get input from users of web applications is using HTML forms. These forms give developers the ability to create text fields, dropdown selectors, radio buttons, checkboxes, and buttons. Using CSS, developers can adjust how the form looks on their particular website/program. JavaScript gives the ability to give the form functionality.

### The form element
All forms within HTML are contained within a `form` element. This element is the container that holds all the input fields, buttons, labels, and others associated with forms. It acts like any container element but contains some attributes that tell the browser what it should do within those fields.

A coded example below of a form containing 2 input fields and a submit button.
```HTML file:basicForm.html fold
<html>
	<head>
		<title>HTML Form</title>
	</head>
	<body>
		<form action="subscribe.php" name="newsletterSubscribe" method="post">
			<label for="firstName">First Name: </label>
			<input type="text" name="firstName" id="firstName"><br>
			<label for="email">Email:
			<input type="text" name="email" id="email"></label><br>
			<input type="submit" value="Subscribe to our newsletter!">
		</form>
	</body>
</html>
```

In the coded example above, you'll see the `form` element has three attributes...
1. `action`: This tells the browser what to do with the user's inputs, often a server-sided script.
2. `name`: This specifies the name that the developer assigned to the form. This attribute is helpful for accessing the form using the DOM.
3. `method`: This takes the value of either `get` or `post` which tells the browser where to send that data. Either in the form of the URL or in the HTTP header.

The form can contain other attributes than just the 3 mentioned above. These include...
* `accept-carset`: This indicates the character sets that the server accepts. If you're not using multilingual content, you don't have to use this.
* `autocomplete`: This indicates if the forms input elements should use autocomplete within the browser.
* `enctype`: This indicates the type of content that the form should submit to the server. For text related data going to the server, it should be set to `text/html`. If you're submitting a file or graphics to the server, then it should be set to `multipart/form-data`.
* `novalidate`: This is a Boolean value to indicate whether the input form should be validated after submitting. If this isn't specified, then the forms are validated by default.
* `target`: This indicates where the response from the server should be displayed after its been submitted. The default (`_self`) is opening the response in the same browser window. For a new window, use `_blank`.

### The label element
The `label` element can be associated with an input field's description. The `for` attribute of the label element takes the value of the id that it should work with. This can be seen in the code example below.
```HTML file:labelElement.HTML fold
<label for="firstName">First Name: </label>
<input type="text" name="firstName" id="firstName">
```

Another method is to nest the form field within the `label` element as seen in the coded example below.
```HTML file:nestLabel.html fold
<label>First Name:
	<input type="text" name="firstName">
</label>
```
The advantage of the above method is not requiring the input field to have an ID.

### The input element
The HTML `input` element is the most fundamental form-related element within HTML. Depending on the value given for the `type` attribute, it makes the browser display several types of input fields.

The most common input field to set is `text` which creates a text input within the browser. The optional `value` attribute assigns a default value to the element. Finally, the `name` attribute is the name that is paired with the value of the form label which can be accessed through the DOM. It's also submitted with the rest of the form values when the form is submitted.

The basic text input field is coded below...
```HTML file:basicTextField.html fold
<input type="text" name="streetAddress">
```

The `input` element in HTML5 gained a lot of new possible `type` attribute values. These allow developers to more precisely specify the type of value that should be provided within an input. It also allows the web browser to provide controls that are better suited to the type of input that's required to do validation and results better in web applications.

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: It's weird that this chapter is focusing a lot on HTML instead of learning about JavaScript. Forms are an area where HTML can reduce the work load, so it's important that JavaScript developers learn what can be done through forms.

The `input` element's possible values for the `type` attribute are seen in the table below.

| Value            | Description                                                                                                           |
| ---------------- | --------------------------------------------------------------------------------------------------------------------- |
| `button`         | A clickable button                                                                                                    |
| `checkbox`       | A checkbox                                                                                                            |
| `color`          | A color picker                                                                                                        |
| `date`           | A date control (year, month, and day)                                                                                 |
| `datetime`       | A date and time control (year, month, day, hour, minute, second, and fraction of a second based on the UTC time zone) |
| `datetime-local` | A date and time control (year, month, day, hour, minute, second, and fraction of a second; no time zone)              |
| `email`          | A field for an email address                                                                                          |
| `file`           | A file-select field and a Browse button                                                                               |
| `hidden`         | A hidden input field                                                                                                  |
| `image`          | A submit button using an image, rather that the default button                                                        |
| `month`          | A month and year control                                                                                              |
| `number`         | A number input field                                                                                                  |
| `password`       | A password field                                                                                                      |
| `radio`          | A radio button                                                                                                        |
| `range`          | An input using a range of numbers, such as a slider control                                                           |
| `reset`          | A reset button                                                                                                        |
| `search`         | A text field for entering a search string                                                                             |
| `submit`         | A submit button                                                                                                       |
| `tel`            | A field for entering a telephone number                                                                               |
| `text`           | Default; a single-line text field                                                                                     |
| `time`           | A control for entering a time (no time zone)                                                                          |
| `url`            | A field for entering a URL                                                                                            |
| `week`           | A week and year control (no time zone)                                                                                |
### The select element
The `select` element in HTML defines either a drop-down or multiselect input. It contains option elements that are choices that the user will have in the `select` control. Below is a coded example of this element.
```HTML file:selectElement.html fold
<select name="favoriteColor">
	<option value="red">Red</option>
	<option value="blue">Blue</option>
	<option value="green">Green</option>
</select>
```

### The textarea element
This element defines a multiline text input field. Below is a coded example.
```html file:textareaElement.html fold
<textarea name="description" rows="4" cols="30"></textarea>
```

### The button element
This element defines another way to create a clickable button. Below is a coded example.
```HTML file:buttonElement.html fold
<button name="myButton">Click the Button</button>
```

The `button` element can be used in place of `input` elements using the `type` attribute set to `submit`. You can also use button elements anywhere you need a button, but don't want a submit action to happen.
<strong><span style="color: yellow">WARNING ⚠</span></strong>: If you don't want the button to submit when a form is clicked, then you can add a `type` attribute of `button`.

## Working with the Form Object
The HTML DOM represents forms using the `Form` object. You can get and set values of form fields, control the action that's taken when someone submits a form, and change the behavior of the form when an event happens.

### Using Form properties
The properties of `form` objects match up with attributes of the `form` element. They're used for getting/setting values of the `form` attributes with JavaScript.

<strong><span style="color: yellow">REMEMBER ❗</span></strong>: DOM objects are representations of HTML pages and their purpose is to give you access to different parts of the document using JavaScript. Anything can be accessed in HTML with this method.

There's techniques for setting/getting the value of a form's properties in Ch.10. You can then access the property you're looking for or wanting to use by using dot notation or the bracket method. Below is a table of form object properties.

| Property        | Use                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `acceptCharset` | Gets or sets a list of character sets that are supported by the server.                                                  |
| `action`        | Gets or sets the value of the `action` attribute of the `form` element.                                                  |
| `autocomplete`  | Gets or sets whether `input` elements can have their values automatically completed by the browser.                      |
| `encoding`      | Tells the browser how to encode the form data (either as text or as a file). This property is synonymous with `enctype`. |
| `enctype`       | Tells the browser how to encode the form data (either as text or as a file).                                             |
| `length`        | Gets the number of controls in the form.                                                                                 |
| `method`        | Gets or sets the HTTP method the browser uses to submit the form.                                                        |
| `name`          | Gets or sets the name of the form.                                                                                       |
| `noValidate`    | Indicates that the form does not need to be validated upon submittal                                                     |
| `target`        | Indicates the place to display the results of a submitted form.                                                          |
To get the value of the name property from the first form in your document, the below example is a good statement to use.
```JS file:firstProperty.js fold
document.getElementByTagName("form")[0].name
```

A common way to access a form is by assigning it an `id` and use `getElemenetById` to select it.

The DOM provides more convenient methods for accessing forms called the forms collection. This collection lets you access the forms document in 2 different ways.
1. **By index number**: When the form element is created in a document, it's assigned an index number, starting at 0. To access the first form in the document, use `document.forms[0]`.
2. **By name**: You can also access forms by the `name` attribute. An example being `document.forms.["subscribeForm"].action`.

## Using the Form object's methods
There's 2 methods that can be used, `reset` and `submit`.

### The reset method
This method clears any changes made to the form's fields that were made after the page is loaded and resets to the default values. An example of this kind of input can be seen below.
```HTML file:resetMethod.html fold
<input type="reset" value="Clear the form">
```

### The submit method
This method causes the form to submit its values according to the properties of the form. An example of this kind of input method can be seen below.
```HTML file:submitMethod.html fold
<input type="submit" value="Submit the form">
```

The following example below shows the use of `submit` and `reset` methods.
```HTML file:submitResetMethodEx.html fold
<html>
	<head>
		<title>Subscribe to our newsletter!</title>
		<script>
			function setFormDefaults() {
				document.forms.subscribeForm.method = 'post';
				document.forms.subscribeForm.target = '_blank';
				document.forms.subscribeForm.action =
					'http://watzthis.us9.list-manange.com/' +
					'subscribe/post?u=1e6d8741f7db587af747ec056&amp;id=663906e3ba';

				document
					.getElementById('btnSubscribe')
					.addEventListener('click', submitForm);
				document
					.getElementById('btnReset)
					.addEventListener('click', resetForm);
			};

			function submitForm() {
				document.forms.subscribeForm.submit();
			}

			function resetForm() {
				document.forms.subscribeForm.reset();
			}
		</script>
	</head>
	<body onload="setFormDefaults();">
		<form name="subscribeForm">
			<h2>Subscribe to our mailing list</h2>
			<label for="mce-EMAIL">Email Address </label>
			<input type="email" value="" name="EMAIL" id="mce-EMAIL"/>
			<button type="button" id="btnSubscribe">Subscribe!</button>
			<button type="button" id="btnReset">Reset</button>
		</form>
	</body>
</html>
```

### Accessing form elements
JavaScript has several ways to access form input fields and values. Their not always created equal and differences of opinion exist as to which is best.
* **Using the index number of form and its input fields**: To access the first input field in the first form, you could use this...
  `document.forms[0].elements[0]`
  Avoid this technique since it relies on the structure of the document and the other of elements within the form should it ever change.
* **Use the name of the form and input field**: This has the benefit of being easy to read and use. It's also supported by ever browser.
  `document.myForm.firstName`
* **Using `getElementById` to select the form and name of the input field to select the input**: This requires you to assign an `id` attribute to the form of the element.
  `<form id="myForm" action="myAction.php">...</form>`
* **Using a unique `id` attribute value on the field to access it directly**": When using this technique, it's good to remember that if you have multiple forms on your page, that each form must have a unique ID.
  `document.getElementById("firstName")`

### Getting and setting form element values
The DOM gives access to form elements' name and values using the name and value properties. Below is an example of form inputs within a single calculator application.
```HTML file:simpleCalculator.html fold
<html>
	<head>
		<title>Math Fun</title>
		<script>
			function registerEvents() {
				document.mathWiz.operator.addEventListener('click', doTheMath, false);
			}

			function doTheMath() {
				let first = parseInt(document.mathWiz.numberOne.value);
				let second = parseInt(document.mathWiz.numberTwo.value);
				let operator = document.mathWiz.operator.value;
				let answer;

				switch (operator) {
					case 'add':
						answer = first + second;
						break;
					case 'subtract':
						answer = first - second;
						break;
					case 'multiply':
						answer = first * second;
						break;
					case 'divide':
						answer = first / second;
						break;
				}
				document.mathWiz.theResult.value = answer;
			}
		</script>
	</head>
	<body onload="registerEvents();">
		<form name="mathWiz">
			<label>First Number: <input type="number" name="numberOne"/></label>
			<br/>
			<label>Second Number: <input type="number" name="numberTwo"/></label>
			<label>Operator:
				<select name="operator">
					<option value="add">+</option>
					<option value="subtract">-</option>
					<option value="multiply">*</option>
					<option value="divide">/</option>
				</select>
			</label>
		<br/>
		<input type="button" name="operate" value="Do the Math!"/><br/>
		<label>Result: <input type="number" name="theResult"/> </label>
		</form>
	</body>
</html>
```

### Validating user input
A most common use case for JavaScript is to check/validate the form input before submitting user input to the server. Form validation provides an extra safeguard against bad/unsafe data making its way into a web application. Also, it provides user with instant feedback if they've made a mistake.

Some most common input validation tasks have been replaced by HTML attributes within HTML5. However, due to some incompatibilities within browsers, it's still good practice to do.

The calculator app example from above, the input type was set to number for the operand units. This should restrict the user from submitting non-numeric values into the fields. But, because the number input type is new, you can't rely on browsers that people are using to support it.

In the above code example, the important thing to notice is the action of the form has been set to the input validation function. The `submit` method of the form runs only after the tests in the input have finished.

The line below does real magic as it may look strange at first, but works.
```JS file:validationExample.js
if (/^\d+$/.test(first) && /^\d+$/.test(second))
```

The characters between `/` and `\` make up a regular expression which is a search pattern that's made up of symbols that represents groups of other symbols. In this case, we're using a regular expression to check whether the values the enter used are both numeric.

```HTML file:formValidationExample.html fold
<html>
	<head>
		<title>Math Fun</title>
		<script>
			function registerEvents() {
				document.mathWiz.operator.addEventListener('click', validate, false);
			}

			function validate() {
				let first = document.mathWiz.numberOne.value;
				let second = document.mathWiz.numberTwo.value;
				let operator = document.mathWiz.operator.value;
				let answer;

				if (/^\d+$/.test(first) && /^\d+$/.test(second)) {
					doTheMath();
				} else {
					alert('Error: Both numbers must be numeric');
				}
			}

			function doTheMath() {
				let first = parseInt(document.mathWiz.numberOne.value);
				let second = parseInt(document.mathWiz.numberTwo.value);
				let operator = document.mathWiz.operator.value;

				switch(operator) {
					case 'add':
						answer = first + second;
						break;
					case 'subtract':
						answer = first - second;
						break;
					case 'multiply':
						answer = first * second;
						break;
					case 'divide':
						answer = first / second;
						break;
				}
				document.mathWiz.theResult.value = answer;
			}
		</script>
	</head>
	<body onload="registerEvents();">
		<div id="formErrors"></div>
		<form name="mathWiz">
			<label>First Number: <input type="text" name="numberOne"/></label><br/>
			<label>Second Number: <input type="text" name="numberTwo"/></label><br/>
			<label>
				Operator:
				<select name="operator">
					<option value="add">+</option>
					<option value="subtract">-</option>
					<option value="multiply">*</option>
					<option value="divide">/</option>
				</select>
			</label>
			<br/>
			<input type="button" name="operate" value="Do the Math!"/><br/>
			<label>Result: <input type="number" name="theResult"/> </label>
		</form>
	</body>
</html>
 ```