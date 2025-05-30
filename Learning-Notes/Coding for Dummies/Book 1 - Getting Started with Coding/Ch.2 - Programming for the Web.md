---
tags:
    - learning-notes
	- code-for-dummies-book-1
	- HTML
obsidianUIMode: preview
---
## Displaying Web Pages on Your Desktop and Mobile Device
* On desktop computers and mobile devices, web pages are displayed by applications called <u>browsers</u>.
	* Google Chrome
	* Mozilla Firefox
	* Apple’s Safari
	* Microsoft Edge
* The first step to becoming a programmer of websites is to peel back the web page and see and play with the code underneath it all.

### Hacking your favorite news site
* Following the steps mentioned in the book, you can modify the code on your favorite news site to say whatever you want.
	* You can use any browser to do this, but it’s suggested to use either Google Chrome or Mozilla Firefox.
		1. Open your favorite news site using one of the browsers mentioned above (example used is HuffPo)
		2. Place the mouse cursor on a static/fixed headline and right click that once which should open a menu. Then, click on Inspect.
		3. Scan the highlighted code carefully for the text of the headline chosen. When found, double click on the text which should allow you to edit the headline.
		4. Insert your name or whatever text you want to the headline and then press enter.
	* When refreshing the page, everything disappears. Why?

### Understanding how the World Wide Web works
* After typing out the URL of the news site of choice into the browser, the following will happen behind the scenes of the browser.
	1. The computer sends your request to the webpage of choice through your router which then distributes internet access throughout the home/workplace.
	2. The router then passes your request onto your ISP (Internet Service Provider). *In the US, the company in charge of this is usually Comcast, Time Warner, AT&T, or Verizon.*
	3. The ISPO then converts the words and characters in the URL that you want into a numerical address (IP Address). Next, the ISP has a digital phonebook, similar to a physical phonebook, called a domain name server that’s used to convert text URLs into IP addresses.
		* An IP Address is a set of four numbers separated by periods (192.168.1.1), just like a physical address. Every computer has one and is unique.
	4. With that IP address located, the ISP knows which server on the internet to forward the request to, and your personal IP is included in the request.
	5. The website’s server receives the request and sends a copy of the webpage code to your computer for the browser of choice to display.
	6. The web browser then renders the code onto the screen.
* When editing the website’s code using the developer tools, you only modified a copy of the website’s code that exists on the computer, thus making it only you can see the change and no one else.
* A tool like ad blocker works the same way by editing the local copy of website code.
	* They are controversial because websites use advertising revenue to pay for operating costs. This can cause websites to demand users to pay to see their content.

### Watching out for your frontend and backend
* Diving deeper into the way the actual website is constructed, the code of sites and programs in general can be divided into four categories depending on the function of the code.
	* <u>Appearance</u>: This is the visual part of the website which includes content and layout with different stylings. This is called Frontend Development which is created by using languages like <u>HTML, CSS, and JavaScript</u>.
	* <u>Logic</u>: This is the opposite of the appearance category as this deals with accessing data. This is called Backend Development which is created by using languages like <u>Ruby, Python, and PHP</u> which can modify the HTML, CSS, and JavaScript that’s displayed to a user.
	* <u>Storage</u>: Storage saves data that is generated by the website/app and the users. This include content, preferences, profile data, and more. This category is part of the backend and is stored in databases like <u>MongoDB and MySQL</u>.
	* <u>Infrastructure</u>: This delivers the website from the server to the user. No one notices this, but it can be when the website or application becomes unavailable from a high traffic of users. This includes software like <u>Apache and Nginx</u>.
* Web developers usually specialize in one or two of the categories mentioned above.
	* Example 1: An engineer might understand frontend and logic languages.
	* Example 2: An engineer might only specialize in databases.
* The rare web developer can be proficient in all 4 making them a full stack developer.
	* A small company might hire someone like this until they need more people who can focus on each part of the website or application.

### Defining web and mobile applications
* Web applications are websites that are visited using a web browser on either a PC, Tablet, or mobile phone.
	* Also called mobile web applications
* Native mobile applications can’t be viewed using a web browser, instead they’re downloaded from an app store (*like Google Play or Apple App Store*) and are designed to run on the specific device.
	* In 2014, people with mobile phones outnumbered people with desktop computers.
	* Mobile device users spend 80% of their time using native mobile applications and 20% browsing mobile websites.
* Many companies are becoming mobile first as the increase of users on mobile phones has risen in the past 15-20 years.

## Coding Web Applications
* Web applications are easier to build than mobile applications.
* The languages used to code basic web applications include <u>HTML, CSS, and JavaScript</u>.
	* Additional features can be added to the websites using languages like <u>Python, Ruby, or PHP</u>.

### Starting with HTML, CSS, and JavaScript
* Simple websites are coded in HTML, CSS, and JavaScript.
	* HTML is used to place text and content on the page.
	* CSS is used to style that content
	* JavaScript is used to add interactive effects

### Adding logic with Python, Ruby, or PHP
* Websites with more advanced functionality (*user accounts, file uploads, e-commerce*) require a programming language to use these kinds of features.
	* Python, Ruby, and PHP are among the popular languages to choose from when doing this kind of work.
* Each language has their own framework to go along side with them.
	* <u>Framework</u>: A collection of generic components that are reused frequently allowing developers to build, test, and launch websites more quickly.
		* An example of this is like using templates that come with Microsoft Word
	* Example of frameworks for the mentioned languages
		* Django and Flask for Python
		* Rails and Sinatra for Ruby
		* Zend and Laravel for PHP

## Coding Mobile Applications
* Mobile applications are the hot topics of today since apps like WhatsApp and Instagram have made billions of dollars over the years.
* Native Mobile Applications can be built by using either or…
	* HTML, CSS, JavaScript
	* Native applications for a specific language
		* Apple devices use <u>Objective-C or Swift</u>
		* Android devices use <u>Java, Kotlin, or Dart</u>
* Between the two options, there’s a few factors to play to consider the following
	* Companies must make sure the mobile version of their web application works across all browsers, screen sizes, and manufacturers.
	* Being able to only run on one platform, native apps are more expensive and take longer to make than mobile web apps.
	* Some devs reported loading issues between mobile web applications and native applications.
	* Users spend more time using native applications and less time with using mobile web apps.
	* Native apps are distributed through an app store (*Google Play or Apple App Store, which needs approval*). Web apps are on the web which don’t need to be downloaded.
* ===FUN TECH INFO===: In one famous example of an app rejected from an app store, Apple blocked Google from launching the Google Voice app in the Apple App Store because it overlapped with Apple’s own phone functionality. Google responded by creating a mobile web app accessible from any browser, and Apple could do nothing to block it.
* Consider the complexity of the application when developing the schedules or menus. Some companies create mobile web applications before creating their mobile app before making the switch.

### Building mobile web apps
* Any website can be viewed with a mobile browser, those websites not optimized for mobile devices look a little weird, as if the regular website font size and image dimensions were decreased to fit on a mobile screen.
* This is done by using HTML, CSS, and JavaScript
	* CSS controls the appearance of the website across devices based on their screen width.
		* Screens with small width (mobile phones), are vertically based layout
		* Screens with a larger width (computers), are horizontally based layout
* The web apps that you use on the browser doesn’t send push notifications but runs in the background if the app is minimized.
* Mobile web frameworks allow you to develop from a base of pre-written code (will be talked about in another book)
	* Bootstrap CSS as an example

### Building native mobile apps
* Native mobile apps can be faster, more reliable, and look more polished than mobile web apps.
*  Since native mobile applications are programs that are installed on the mobile device, they can be used in more situations without an Internet connection.
* Native mobile apps can take advantage of features that run in the background while the app is minimized, such as push notifications, and communicate with other apps, and these features are not available when creating a mobile web app.
* Two popular cross-platform frameworks are Fluttter and React Native.
	* Both allow writing cross-platform code, either using JavaScript (*in the case of React Native*) or Dart (*in the case of Flutter*).

## Deploying Web Applications in the Cloud
* In the early days of the web and mobile apps, making your web applications and mobile applications available to the world meant that you needed to buy, configure, and maintain enough physical hardware (in the form of expensive web servers) to be able to handle your busiest days.
	* f a web app or mobile app suddenly became so popular that the servers hosting it slowed down during peak times, the only solution was to purchase yet more hardware.
* Cloud computing is revolutionizing how software runs over the web by making computing power available as a service. What that means is that instead of the creator of an app needing to anticipate and monitor demand for their app and increase (or decrease) the power of the computers running the app, cloud computing makes computing power more like a utility.