---
tags:
    - learning-notes
    - code-for-dummies
    - JavaScript
obsidianUIMode: preview
---
> "The Web does not just connect machines, it connects people."
> -- Tim Berners - Lee

AJAX is a technique for making web pages more dynamic by sending and receiving data in the background while users interact with web pages. JSON had become the standard data format when using AJAX applications.

## Working behind the scenes with AJAX
*Asynchronous JavaScript + XML* (AJAX) is a term that's used to describe the method of using JavaScript, the DOM, HTML, and the `XMLHttpRequest` object to refresh parts of a web page with live data without the need to refresh the entire web page.

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: AJAX was first implemented in a large scale by Google using Gmail back in 2004 and given the name by Jesse James Garret in 2005.

The DOM changes the page dynamically. AJAX was made to use the `XMLHttpRequest` object to retrieve data from the server asynchronously without blocking the execution of JavaScript for the rest of the page.

Although it originally relied on data formatted as XML, it's more common now for AJAX applications to use JSON (*JavaScript Object Notation*).

### AJAX examples
When developers first started to use AJAX, it became a hallmark of what was labeled Web 2.0. The most common way for web pages to show dynamic data before AJAX was introduced was by downloading a new webpage from a server. An example of this is to look at how craigslist works/worked.

To navigate through categories of listings/search results, you click links that cause the entire page to refresh and load the content that was requested. Comparing the old style navigation of the site to something like Google Slides. AJAX in this instance loads new content into a single part of the screen while the navigation bars remain static.

AJAX is also great for creating live data elements within a web page. Before, if you wanted to display live data within a chart or table or view your email inbox, you needed to use something like Adobe Flash or have the webpage automatically refresh. Now, with using AJAX, data is updated through the asynchronous process that runs in the background and updates only the elements that need to be updated.

A good example of this is looking at Weather Underground's Wundermap. This map shows constantly changing weather and updating data overlays. It's data is being updated from remove servers using AJAX.

### Viewing AJAX in action
Using Weather Underground's Wundermap, you can use Chrome's/Firefox's Developer Tools window and open the Network tab. From there, this tab will show you all the network activity within the webpage. This includes downloading the page's HTML, CSS, JavaScript, and images. After the web page is finished loading, then the asynchronous HTTP requests makes AJAX possible.

Follow these steps in order to see what was described above...
1. Open your web browser and go to wunderground.com/wundermap.
2. Open the Chrome/Firefox Developer tools
3. Open the Network Tab
4. Click on one of the rows in the Name column of the Networks tab
5. Click through the tabs (Headers, Preview, Response, etc..) in the detailed data pane and examine the data.
6. Select and copy the value of the Request URL from one of the items you've inspected.
7. Open a new tab within your browser and paste the Request URL into the address bar.
8. Compare the results of opening the Request URL in a new tab with the results shown in the Response tab of the developer tools.

From what you can see, there's no magic to AJAX. The JavaScript on the page is requesting and receiving data from a server. Everything is happening behind the scenes and is available for inspection through Developer Tools on any browsers used today.

### Using the `XMLHttpRequest` object
This object provides a way for browsers to request data from a URL without the need of refreshing the page.

The object was created and first implemented by Microsoft in Internet Explorer and has since become the standard that's been adopted by every major web browser.

You can use methods and properties of this object to retrieve data from a remove or local server. Despite the name the `XMLHttpRequest` object can get other data besides XML, protocols, and HTTP data.

The below coded example shows how you can use this object to load the contents of an external text document containing HTML into the current HTML document.
```HTML file:XMLHttpRequestExample.html fold
<html>
	<head>
		<title>Loading External Data</title>
		<script>
			window.addEventListener('load', init, false);
			function init(e) {
				document
					.getElementById('myButton')
					.addEventListener('click', documentLoader, false)'
			}

			function reqListener() {
				console.log(this.responseText);
				document.getElementById('content').innerHTML = this.responseText;
			}

			function documentLoader() {
				let oReq = new XMLHttpRequest();
				oReq.onload = reqListener;
				oReq.open('get', 'loadme.txt', true);
				oReq.send();
			}
		</script>
	</head>
	<body>
		<form id="myForm">
			<button id="myButton" type="button">Click to Load</button>
		</form>
		<div id="content"></div>
	</body>
</html>
```

The heart of the document is the `documentLoader` function
```JS file:documentLoader.js fold
function documentLoader() {
	var oReq = new XMLHttpRequest();
	oReq.onload = reqListener;
	oReq.open = ("get", "loadme.txt", true);
	oReq.send();
}
```

The first line of code within the above function creates the new `XMLHttpRequest` object and gives it the name of `oReq`. The methods and properties of the `XMLHttpRequest` are accessible through the `oReq` object.

The second line assign a function of `reqListener` to the `onload` event of the `oReq` object. The purpose is to cause the `reqListener` function to be called when `oReq` loads a/the document.

The first line uses the `open` method to create a request, in this case the `HTTP GET` method calling for the file of `loadme.txt`. The next parameter is the `async` argument which specifies whether the request should be asynchronous or not. If set to `false`, the `send` method won't return until that request is complete. If set to `true`, notifications of the completion of the request will be provided through event listeners. The event listener is set to listen for the `load` event.

<strong><span style="color: yellow">WARNING ⚠</span></strong>: It's unlikely you'll run into a situation where you want to set the `async` argument to `false`. Some browsers have begun to ignore the argument if set to `false` and instead treat it as `true` either way because of the bad effect of the user experience that these requests have.

The last line from the `documentLoader` function sends the request that was created with the `open` method.

<strong><span style="color: yellow">TECHNICAL 🤓</span></strong>: The `open` method will get the latest version of the file that was requested. Live data applications use loops to repeatedly request updated data from a server using AJAX.

### Working with the same-origin policy
If you save the HTML to a document that was coded from the above example and open it in a browser, you'll get some errors when you open the browser's developer console.

The program is called *same-origin policy*. To prevent web pages from causing users to unknowingly download code that could harm their system by using the `XMLHttpRequest`, browsers will return an error by default whenever a script loads from a URL that isn't from the same origin.

The same-origin policy also applies to files on your system. If it didn't then your system would be compromised.

There's no need to worry about the examples from this chapter from hurting your system as it's just an example.

The first way around this policy is to put some HTML in the file containing the `documentLoader` function and the text file on the same system. The other way is to start your browser with same-origin policies temporarily disabled.

<strong><span style="color: yellow">WARNING ⚠</span></strong>: The instructions below allow you to test on your own files on your computer. Don't surf the web while this is disabled as it can harm your system.

To disable same-origin policy on Windows, follow these steps...
1. Close the Chrome/Firefox browser if it's already open
2. Open a Command Prompt and navigate to the folder where Chrome is installed.
3. Type the following command to launch the browser...
```shell file:disable-same-origin fold
Chrome.exe --disable-web-security
```

As the browser starts up, you'll be able to run files containing AJAX requests locally until you close the browser. One the browser is closed and then re-opened, the security restrictions you had will be re-enabled.

### Using CORS, the silver bullet for AJAX requests
It's common for a web application to make requests to different servers in order to retrieve data for the user. An example of this would be many sites and mobile apps use Google Maps through Google's Map Platform API.

For transactions between servers to be secure, mechanisms have been created for browsers and servers to work out the differences and establish a trust with each other. The best method for this is called *Cross-Origin Resource Sharing* (CORS).

To see this in action, visit Weather Underground's Wundermap using any browser of your choice. After the page is loaded, right click the page and click on `inspect` to open the Developer Tools and then select the Network tab. Click on a request where `Name` starts with `"stationdata?"` and the `Type` is `xhr`.

Next, click the headers tab and you'll see the following text in the HTTP header.
`Access-Control-Allow-Origin: *`

This is the response header that the particular server is configured to send to. The `*` value after the colon indicates that the server will accept requests from any origin. If the owners of the website wanted to restrict access of the data to only specific users or authenticated users, they could by using CORS.

## Putting Objects in Motion with JSON
In an above example, you used AJAX to open and display a text document that contained a snippet of HTML. Another common use for AJAX is to request and receive data for processing by the browser.

An example of this would be using gasbuddy's website as they use a map from Google along with data about gas prices to present a simple and up-to-date view of prices in different locations.

If you view the network tab of their website, you'll find some requests that have responses that look like the example below.
```JSON file:gasBuddyAJAXResponse.js fold
([{id:"tuwtvtuvvvv",base:[351289344,822599680],zrange:[11,11], layer:"m@288429816",features:[{ id:"17243857463485476481",a:[0,0],bb:[-8,-8,7,7,-47,7,48,22,-41,19,41,34],c:"{1: {title:\"Folsom Lake State Recreation Area\"},4:{type:1}}"}]},{id:"tuwtvtuvvvw", zrange:[11,11],layer:"m@288429816"},{id:"tuwtvtuvvwv",base:[351506432,824291328], zrange:[11,11],layer:"m@288429816",features:[{id:"8748558518353272790",a:[0,0], bb:[-8,-8,7,7,-41,7,41,22],c:"{1:{title:\"Deer Creek Hills\"},4:{type:1}}"}]}, {id:"tuwtvtuvvww",zrange:[11,11],layer:"m@288429816"}])
```

Taking the above data from the block and reformatting it, you get something that looks a little familiar...
```JS file:gasBuddyJSResponse.js fold
{id:"tuwtvtuvvvv",
base:[351289344,822599680],
zrange:[11,11],
layer:"m@288429816",
features:[{
id:"17243857463485476481",
a:[0,0],
bb:[-8,-8,7,7,-47,7,48,22,-41,19,41,34],
c:"{
1:{title:\"Folsom Lake State Recreation Area\"},
4:{type:1}
}"}
]}
}
```

Look at the format of the data, you can see it looks like the `name: value` format of a JavaScript literal.

The reason JSON is easy to use is because it's already in a format that JavaScript can work with. Another example of this is a JSON file continuing information about the book.
```JSON file:bookInfo.json fold
{ "book_title": "Coding All-in-One For Dummies",
"book_author": "Chris Minnick",
"summary": "Everything beginners need to know to start coding.",
"isbn":"978-1119889564"
}
```

The coded example below shows how the data above can be loaded into a webpage using JavaScript and displaying it using HTML.
```HTML file:JsonWithJSwithHTML.html fold
<html>
	<head>
		<title>Displaying JSON Data</title>
		<script>
			window.addEventListener('load', init, false);
			function init(e) {
				document
					.getElementById('myButton')
					.addEventListener('click', documentLoader, false);
			}

			function reqListener() {

				// convert the string from the file to an object with JSON.parse
				var obj = JSON.parse(this.responseText);

				// display the object's data like any object
				document.getElementById('book_title').innerHTML = obj.book_title;
				document.getElementById('book_author').innerHTML = obj.book_author;
				document.getElementById('summary').innerHTML = obj.summary;
			}

			function documentLoader() {
				var oReq = new XMLHttpRequest();
				oReq.onload = reqListener;
				oReq.open('get', 'listing14-5.json', true);
				oReq.send();
			}
		</script>
	</head>
	<body>
		<form id="myForm">
			<button id="myButton" type="button">Click to Load</button>
		</form>
		<h1>Book Title</h1>
		<div id="book_title"></div>
		<h2>Authors</h2>
		<div id="book_author"></div>
		<h2>Summary</h2>
		<div id="summary"></div>
	</body>
</html>
```

The key to displaying any JSON data that's brought into a JavaScript document from an external source is to convert it from a string to an object using the `JSON parse` method. After that, you can access the values from within that file using dot or bracket notation.