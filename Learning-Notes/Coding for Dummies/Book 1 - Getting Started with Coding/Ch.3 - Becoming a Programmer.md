---
tags:
  - ReadingNotes
  - WebDev
---
Programming is a skill that can be learned by anyone.

## Writing Code Using a Process
* Writing code is much like painting, furniture making, or cooking — it isn’t always obvious how the end product was created.
	* <u>Waterfall</u>: A set of sequential steps followed to create a program.
	* <u>Agile</u>: A set of iterative steps followed to create a program.
* Example from the book…
	*  Imagine that you want to build a restaurant app that does the following two things..
		1. It displays restaurant information, such as the hours of operation and the menu.
		2. It allows users to make or cancel reservations.
	* Using the <u>waterfall method</u>, you define everything the app needs to do:
		1. You design both the information-display and the reservation parts of the app
		2. Code the entire app
		3. Release the app to users
		* This method demands that the developer code and release the entire app at once, but since completing a large project takes an enormous amount of time, changes in technology may occur before the finished product arrives.
	* Using the <u>agile method</u>…
		1. define, design, and code only the information-display portion of the app
		2. Release the app to users
		3. Collect feedback
		* This method stresses shorter development times and has increased in popularity as the pace of technological change has increased.

===FUN TECH INFO===: The US Healthcare website was released in October 2013 using the waterfall style method. Testing of all the code occurred in September 2013. The tests of the website occurred too late and weren’t comprehensive enough, resulting in not enough time to fix errors/bugs before launching the site publicly.

===REMEMBER===: On average, you’ll spend much more time researching, designing, and debugging your app than doing the actual coding, which is the opposite of what you might expect.

Coding an app or website involves <u>4 steps</u>
1. Researching what you want to build
2. Designing your app/website
3. Coding the app/website
4. Debugging the code for the app/website

### Researching what you want to build
* Before writing any code, it helps to do some investigating and research. Ask yourself the following questions…
	1. What similar website/app already exists? What technology was used to build it?
	2. Which features should I include — and more importantly exclude — in my app?
	3. Which providers can help create these features?
		* *For example, companies like Google, Yahoo, Microsoft, or others may have software that you could incorporate into your app.*
	* When conducting market research and answering the three preceding questions, using Google to search is usually the best choice.
		* IE: Searching `resturant reservation app` on Google to view different examples and get ideas.
	* You want to research exactly what kinds of restaurant information you need to provide and how extensive the reservation system portion of the app should be.

### Designing your app
* Your app’s visual design incorporates all of your research and describes exactly how your users will interact with every page and feature.
* At this stage of the process, a general web designer, illustrator, or user interface specialist will help create visual designs for the app.
* There’s two types of visual designs
	1. <u>Wireframes</u>: These are low-fidelity website drawings that show structurally the ways your content and your site’s interface interact.
		* Can use either **Figma**, Photoshop, or **AdobeXD**.
	2. <u>Mockups</u>: These are high-fidelity website previews that include colors, images, and logos.
		* A good place to look for mockups would be Awwwwards, searching on Google, or Dribbble
* In addition to visual design, complex apps also have technical designs and decisions to finalize.

### Coding your app
* With research and design done, you’re now ready to code your application. In everyday web development, you begin by choosing which pages and features to start coding.
	* Knowing how much to code and when to stop can be a tough thought.
	* From receiving feedback, if no one likes your app or thinks it’s useful, it’s best to find out as soon as possible.
		* It’s a good idea to write the minimum code necessary and then add to it.
			*  It’s better to just create the main menu and then later create the drop-down menu.
* Projects can involve frontend developers, who write code to design the appearance of the app, and backend developers, who code the logic and create databases.
* Someone who does both frontend and backend development is considered a “full stack developer”.

### Debugging your code
* Debugging is going to be a natural part of creating an application/website.
* Debugging can be frustrating, the three common mistakes to watch out for…
	1. <u>Syntax Errors</u>: Errors caused by misspelling words/commands
	2. <u>Logic Errors</u>: Your syntax is correct, *but* the program behaves differently than you expected, such as when the prices of the items in the shopping cart of an e-commerce site don’t add up to the correct total.
	3. <u>Display Errors</u>: These are common mainly in web applications. Your program might run and work properly, but it won’t appear properly.
* ===FUN FACT===: The word `debugging` was popularized in the 1940s by Grace Hopper, who fixed a computer error **by literally removing a moth from a computer**.

## Picking Tools for the Job
* You can develop websites either offline, by working with an editor, or online, with a web service such as [CodeSandbox.io](https://codesandbox.io/) or [codepen.io](https://codepen.io).
* You don’t have to download and install any software to start coding, you don’t have to find a web host to serve your web pages, and you don’t need to upload your web page to a web host.

### Working offline
* To code offline, you need the following…
	* <u>Editor</u>: This refers to the text editor you use to write all the code this book covers, including HTML, CSS, JavaScript, Ruby, Python, and PHP. Either use Notepad, Notepad++, or VSCode.
	* <u>Browser</u>: Many browsers exist, including Chrome, Firefox, Safari, Microsoft Edge, and Opera. You can use any up-to-date browser.
	* <u>Web Host</u>: In order for your website code to be accessible to everyone on the Internet, you need to host your website online. Something like [Weebly](https://www.weebly.com/), [Wix](https://www.wix.com/), [Google Sites](https://sites.google.com), or [Google Drive](https://www.google.com/drive/).