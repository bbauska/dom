---
title: |
  DOM Document Object Model
  by Brian Bauska, Systems Analyst
author: "bbauska"
date created: "05/12/25 Mon 12+pm"
date last editted: "05/12/25 Mon 8+pm"
date last editted: "05/13/25 Tue 9+pm"
output: 
  markdown:
    with some style
---

<ol>
  <li><a href="D-01">01. JavaScript - How to Manipulate DOM Elements?</a></li>
  <li><a href="D-02">02. How to Add a <b><mark>Class</mark></b> to <b><mark>DOM Element</mark></b> in JavaScript?</a></li>
  <li><a href="D-03">03. How to select DOM Elements in JavaScript?</a></li>
  <li><a href="D-04">04. How to get all ID of the DOM elements with JavaScript?</a></li>
  <li><a href="D-05">05. JavaScript – How to Get the Data Attributes of an Element?</a></li>
  <li><a href="D-06">06. How To Get Element By Class Name In JavaScript?</a></li>
  <li><a href="D-07">07. How to Get Value by Class Name using JavaScript?</a></li>
  <li><a href="D-08">08. How to Get Domain Name From URL in JavaScript?</a></li>
  <li><a href="D-09">09. How to get protocol, domain and port from URL using JavaScript?</a></li>
  <li><a href="D-10">10. How to Extract the Host Name from URL using JavaScript?</a></li>
  <li><a href="D-11">11. How to Get the Current URL using JavaScript?</a></li>
  <li><a href="D-12">12. How to get URL Parameters using JavaScript?</a></li>
  <li><a href="D-13">13. How to parse URL using JavaScript?</a></li>
  <li><a href="D-14">14. Manipulating HTML Elements with JavaScript</a></li>
  <li><a href="D-15">15. How to use innerHTML in JavaScript?</a></li>
  <li><a href="D-16">16. JavaScript innerHTML</a></li>
</ol>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ readme.md of dom ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1 align="center">DOM</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-01">01 JavaScript - How to Manipulate DOM Elements?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <b><mark>DOM</mark></b> stands for the <b><mark>Document Object Model (DOM)</mark></b>, which 
allows us to interact with the document and change its structure, style, and content. We can use 
the <b><mark>DOM</mark></b> to change the content and style of an HTML element by changing its properties.</p>

<p>We can manipulate or change the <b><mark>DOM elements</mark></b> by using the following methods:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1. Change the Content of an Element</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can change the content inside an HTML element using JavaScript. The two most common 
properties for this are <b><mark>innerHTML</mark></b> and <b><mark>textContent:</mark></b></p>
<ul>
  <li><b><mark>innerHTML</mark></b>: Allows you to get or set the HTML content inside an element.</li>
  <li><b><mark>textContent</mark></b>: Allows you to get or set the text content inside an 
    element, ignoring any HTML tags.</li>
</ul>

```
<body>
  <div id="example1">This is the original content using <b><mark>innerHTML</mark></b>.</div>
  <div id="example2">This is the original text content using <b><mark>textContent</mark></b>.</div>
  <button onclick="changeContent()">Change Content</button>
  <script>
  // Function to change content
  function changeContent() {
    document.getElementById("example1").innerHTML = 
      "<strong>This is changed using innerHTML!</strong>";
    document.getElementById("example2").textContent = 
      "This is changed using textContent!";
    }
  </script>
</body>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 01.  change content using innerHTML ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image001.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image001.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>In this example</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li><b><mark>innerHTML</mark></b> changes the entire content of an element, including HTML tags. 
      In this case, we replace the content of the first <b><mark>div</mark></b> with bold text 
	  using <b><mark>&lt;strong&gt;</mark></b>.</li>
  <li><b><mark>textContent</mark></b> changes only the text inside the element, ignoring any HTML 
    tags. The second <b><mark>div</mark></b> is updated with plain text, without any HTML formatting.</li>
  <li>The first <b><mark>div</mark></b> shows "This is the original content using <b><mark>innerHTML</mark></b>."</li>
  <li>The second <b><mark>div</mark></b> shows "This is the original text content using <b><mark>textContent</mark></b>."</li>
  <li>After clicking the "Change Content" button.</li>
  <li>The first <b><mark>div</mark></b> will display "This is changed using <b><mark>innerHTML</mark></b>!" 
      with bold text.</li>
  <li>The second <b><mark>div</mark></b> will display "This is changed using <b><mark>textContent</mark></b>!" 
      with plain text.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2. Manipulate the Class Attribute</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can add, remove, or toggle <b><mark>classes</mark></b> on an element using JavaScript. 
This is helpful for styling or applying animations.</p>
<ul>
  <li><b><mark>classList.add()</mark></b>: Adds a <b><mark>class</mark></b> to an element.</li>
  <li><b><mark>classList.remove()</mark></b>: Removes a <b><mark>class</mark></b> from an element.</li>
  <li><b><mark>classList.toggle()</mark></b>: Toggles a <b><mark>class</mark></b> 
    (adds it if it's not present, removes it if it is).</li>
</ul>

```
<html>
<head>
  <style>
    .highlight {
      color: red;
      font-weight: bold;
    }
    .bold {
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div id="example" class="bold">This is a text element with the "bold" class.</div>

  <button onclick="addClass()">Add 'highlight' Class</button>
  <button onclick="removeClass()">Remove 'bold' Class</button>
  <button onclick="toggleClass()">Toggle 'highlight' Class</button>
  <script>
    function addClass() {
      document.getElementById("example").classList.add("highlight");
    }
    function removeClass() {
      document.getElementById("example").classList.remove("bold");
    }
    function toggleClass() {
      document.getElementById("example").classList.toggle("highlight");
    }
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 02. manipulate class ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image002.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a><!-- image002.gif -->
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>In this example</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li>Adding a Class (<b><mark>addClass()</mark></b>): When you click the "Add 'highlight' Class" 
      button, the highlight class is added to the div element with the id="example". This changes 
	  the text color to red and makes it bold (as defined in the CSS).</li>
  <li>Removing a Class (<b><mark>removeClass()</mark></b>): When you click the "Remove 'bold' Class" 
      button, the bold class is removed from the div, which removes the bold styling from the text.</li>
  <li>Toggling a Class (<b><mark>toggleClass()</mark></b>): When you click the "Toggle 'highlight' 
      Class" button, the highlight class is either added or removed, depending on whether it's 
	  already present. If the class is present, it will be removed; if not, it will be added.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3. Set CSS Styles Using JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can directly manipulate the CSS styles of an element using the style property. This allows you 
to dynamically change how elements appear on the page.

```
// Changing multiple CSS properties
document.getElementById("demo").style.color = "red";
document.getElementById("demo").style.fontSize = "20px";
// Adding more than one style
document.getElementById("demo").style.cssText = "color: blue; font-size: 18px;";
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4. Create, Add, and Remove Elements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Sometimes, you need to create new elements, add them to the DOM, or remove existing ones. You can 
do this easily with the following methods;
<ul>
  <li><b><mark>document.createElement()</mark></b>: Creates a new element.</li>
  <li><b><mark>appendChild()</mark></b>: Adds a new element to a parent element.</li>
  <li><b><mark>removeChild()</mark></b>: Removes a child element from a parent.</li>
</ul>

```
// Create a new element
let newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";
// Add the new element to the DOM
document.body.appendChild(newDiv);
// Remove an element from the DOM
document.body.removeChild(newDiv);
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>5. Insert Elements at a Specific Position</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can insert new elements at specific positions relative to existing elements using methods 
like <b><mark>insertBefore()</mark></b>.

```
// Create a new element
let newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";

// Find an existing element to insert before
let referenceNode = document.getElementById("referenceElement");

// Insert the new element before the reference element
document.body.insertBefore(newDiv, referenceNode);
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>6. Manipulate Element Attributes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can easily get, set, or remove the attributes of an HTML element using the following methods:
<ul>
  <li><b><mark>getAttribute()</mark></b>: Retrieves the value of an attribute.</li>
  <li><b><mark>setAttribute()</mark></b>: Sets a new value for an attribute.</li>
  <li><b><mark>removeAttribute()</mark></b>: Removes an attribute.</li>
</ul>

```
// Get the value of an attribute
let src = document.getElementById("image").getAttribute("src");

// Set a new value for an attribute
document.getElementById("image").setAttribute("src", "new-image.jpg");

// Remove an attribute
document.getElementById("image").removeAttribute("src");
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>7. Manipulate Data Attributes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
HTML5 introduced data attributes, which are custom attributes that you can use to store extra 
information about an element. These are particularly useful for adding data to an element 
without affecting its visual structure.
<ul>
  <li><b><mark>dataset</mark></b>: A special property in JavaScript that allows you to access data attributes.</li>
</ul>

```
// Setting a data attribute
document.getElementById("demo").dataset.userId = "12345";
// Getting a data attribute
let userId = document.getElementById("demo").dataset.userId;
console.log(userId); // Outputs: 12345
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-02">02 How to Add a <b><mark>Class</mark></b> to <b><mark>DOM Element</mark></b> in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Adding a class to a <b><mark>DOM (Document Object Model)</mark></b> element in JavaScript is a fundamental 
task that enables developers to dynamically manipulate the appearance and behavior of web pages. 
Classes in HTML provide a powerful way to apply CSS styles or JavaScript functionality to multiple 
elements at once.

By using JavaScript, you can easily add, remove, or toggle classes on elements, making your web 
applications more interactive and responsive to user actions.

These are the following approaches:

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Table of Content</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li>Using <b><mark>classList</mark></b> Property</li>
  <li>Using <b><mark>className</mark></b> Property</li>
  <li>Using <b><mark>classList</mark></b> Property</li>
</ul>

<p>In this approach, we are using <b><mark>classList</mark></b> property to add the class into the 
<b><mark>DOM element</mark></b>. It returns the class name as a <b><mark>DOMTokenList</mark></b> 
object. It has a method called “add” which is used to add class name to elements. We will access 
the <b><mark>div</mark></b> using the <b><mark>getElementById</mark></b> and we will use the add property of 
<b><mark>classList</mark></b> to add a class.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
element.classList.add("className")
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: This example shows the implementation of the above-explained approach.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html>
<head>
  <style>
    .geek {
      background-color: green;
      font-size: 50px;
    }
  </style>
</head>
<body>
  <button onclick="myClass()">Try it</button>
  <div id="gfg">Geeks for Geeks</div>
  <script>
    function myClass() {
      let elem = document.getElementById("gfg");

      // Adding class to div element 
      elem.classList.add("geek");
    } 
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 03. manipulate class ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image003.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image003.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using <b><mark>className</mark></b> Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In this approach, we are using the <b><mark>className</mark></b> property. This property returns the 
<b><mark>className</mark></b> of the element. If the element has already a class then it will simply 
add another one to it or else it will append our new class to it.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>HTMLElementObject.className</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: This example shows the implementation of the above-explained approach.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html>
<head>
  <style>
    .geekClass {
      background-color: green;
      text-align: center;
      font-size: 50px;
    }
  </style>
</head>
<body>
  <div id="gfg">
      Geeks For Geeks
  </div>
  <button onclick="myClassName()">Add Class</button>
  <script>
    function myClassName() {
      let element = document.getElementById("gfg");
      // Adding the class geekClass to element 
      // with id gfg space is given in className 
      // (" geekClass") as if there is already 
      // a class attached to an element than our 
      // new class won't overwrite and will append 
      // one more class to the element 
      element.className += " geekClass";
    } 
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 04.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image004.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image004.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-03">03. How to select DOM Elements in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Selecting <b><mark>DOM (Document Object Model)</mark></b> elements is a fundamental aspect of web 
development with JavaScript. It allows developers to interact with and manipulate elements 
on a webpage dynamically. Proper selection of elements is crucial for tasks such as updating 
content, adding event listeners, or modifying styles.</p>

<p>Below are the approaches to select DOM elements in JavaScript:</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Table of Content</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li><href id="#01">1. Using <b><mark>getElementById</mark></b></a></li>
  <li><href id="#02">2. Using <b><mark>getElementsByClassName</mark></b></a></li>
  <li><href id="#03">3. Using <b><mark>getElementsByTagName</mark></b></a></li>
  <li><href id="#04">4. Using <b><mark>querySelector</mark></b></a></li>
  <li><href id="#05">5. Using <b><mark>querySelectorAll</mark></b></a></li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="01">1. Using <b><mark>getElementById</mark></b></h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This method selects a single element by its unique ID attribute.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>document.getElementById('id')</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, 
    initial-scale=1.0">
  <title>getElementById Example</title>
</head>
<body>
  <h1 id="gfg">GeeksForGeeks</h1>
  <script>
  // styling the h1 tag
  const element = document.getElementById('gfg');
    element.style.color = "green";
    element.style.textAlign = "center";
    element.style.margin = "30px";
    element.style.fontSize = "30px";
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 05. GeeksForGeeks in green ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image005.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image005.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="02">2. Using <b><mark>getElementsByClassName</mark></b></h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This method selects elements based on their class attribute. It returns a collection of elements 
with the specified class name.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>document.getElementsByClassName('class')</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
    content="width=device-width, initial-scale=1.0">
  <title>getElementsByClassName Example</title>
</head>
<body>
  <h1 class="selector">GeeksForGeeks</h1>
  <h2 class="selector">DOM selector in JavaScript</h2>
  <script>
    const elements = 
      documSizeent.getElementsByClassName('selector');
      elements[0].style.color = "green";
      elements[1].style.color = "red";
      elements[0].style.textAlign = "center";
      elements[1].style.textAlign = "center";
      elements[0].style.marginTop = "60px";
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 06.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image006.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image006.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="03">03. Using <b><mark>getElementsByTagName</mark></b></h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This method selects elements based on their tag name. It returns a collection of elements with the 
specified tag name.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>document.getElementsByTagName('tag')</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
    content="width=device-width, initial-scale=1.0">
  <title>getElementsByTagName Example</title>
</head>
<body>
  <p>Thanks for visiting GFG</p>
  <p>This is showing how to select DOM element using tag name</p>
  <script>
    const paragraphs = document.getElementsByTagName('p');
      paragraphs[0].style.color = "green";
      paragraphs[1].style.color = "blue";
      paragraphs[0].style.fontSize = "25px";
      paragraphs[0].style.textAlign = "center";
      paragraphs[1].style.textAlign = "center";
      paragraphs[0].style.marginTop = "60px";
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 07.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image007.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image007.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="04">04. Using querySelector</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>This method selects the first element that matches a specified CSS selector. It returns only 
one element.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>document.querySelector('selector')</pre>
<h4>Example:</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
    content="width=device-width,
      initial-scale=1.0">
  <title>querySelector Example</title>
</head>
<body>
  <div class="gfg">GeeksForGeeks</div>

  <script>
    const element = 
      document.querySelector('.gfg');
      element.style.color = "green";
      element.style.textAlign = "center";
      element.style.margin = "30px";
      element.style.fontSize = "30px";
  </script>
</body>
  
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 08.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image008.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image008.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3 id="05">05. Using querySelectorAll</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Similar to <b><mark>querySelector</mark></b>, but it returns a <b><mark>NodeList</mark></b> containing 
all elements that match the specified CSS selector.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>document.querySelectorAll('selector')</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" 
    content="width=device-width, initial-scale=1.0">
  <title>querySelectorAll Example</title>
</head>
<body>
  <h1 class="selector">GeeksForGeeks</h1>
  <p class="selector">
    This is showing how to select DOM element
    using tag name
  </p>
  <script>
    const elements = document.querySelectorAll('.selector');
      elements[0].style.color = "green";
      elements[1].style.color = "red";
      elements[0].style.textAlign = "center";
      elements[1].style.textAlign = "center";
      elements[0].style.marginTop = "60px";
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 09. how to select dom element using tag name ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image009.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image009.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-04">04. How to get all ID of the DOM elements with JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Given a HTML document and the task is to get the all ID of the DOM elements in an array. There are 
two methods to solve this problem which are discusses below: 
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Approach 1:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
First select all elements using <b><mark>$(‘*’)</mark></b> selector, which selects every element 
of the document. Use <b><mark>.each()</mark></b> method to traverse all elements and check if it 
has an ID. If it has an ID then push it into the array.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: This example implements the above approach.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>
    How to get all ID of the DOM
    elements with JavaScript ?
  </title>
  <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
  </script>
</head>
 
<body>
  <h1 style="color: green">
    GeeksforGeeks
  </h1>
  <p>
    Click on the button to get 
    all IDs in an array.
  </p>
  <button onclick="muFunc()">
    Click Here
  </button>
 
  <p id="GFG"></p>
   <script>
     let res = document.getElementById("GFG");
     function muFunc() {
       let ID = [];
       $("*").each(function () {
         if (this.id) {
           ID.push(this.id);
         }
       });
       res.innerHTML = ID;
     }
   </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 10. click to get all ids in an array ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image010.gif?raw=true"
    loading="lazy"
    style="width:30%;"
    title=""
    alt="." />
</a>
</p>
<!-- image010.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Approach 2:</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li>First select all elements using <b><mark>$(‘*’)</mark></b> selector, which selects every 
    element of the Document.</li>
  <li>Use <b><mark>.map()</mark></b> method to traverse all element and check if it has ID.</li>
  <li>If it has ID then push it in the array using <b><mark>.get()</mark></b> method.</li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: This example implements the above approach.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>
    How to get all ID of the DOM
    elements with JavaScript ?
  </title>
  <script src= 
    "https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
  </script>
</head>
<body>
  <h1 style="color: green">
    GeeksforGeeks
  </h1>
  <p>
    Click on the button to get 
    all IDs in an array.
  </p>
   <button id="Geeks" onclick="muFunc()">
    Click Here
  </button>
  <p id="GFG"></p>
  <script>
    let res = document.getElementById("GFG");
    function muFunc() {
      let ID = [];
    ID = $("*").map(function() {
      if (this.id) {
        return this.id;
      }
    }).get();
    res.innerHTML = ID;
  }
  </script>
</body>
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 11. click to get all id's in an array ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image011.gif?raw=true"
    loading="lazy"
    style="width:30%;"
    title=""
    alt="." />
</a>
</p>
<!-- image011.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-05">05. JavaScript – How to Get the Data Attributes of an Element?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Here are the various methods to get the data attributes of an element using JavaScript
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1. Using dataset Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The dataset property in JavaScript allows you to access all data attributes of an HTML element as a DOMStringMap object. It simplifies retrieving, modifying, or interacting with custom data stored in attributes like data-id or data-name.
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>
const e =  document.getElementByID('demo') // Accessing the element 
const dataId  = e.dataset.dataID //Access the data-id attribute 
</code></pre>

```
<!DOCTYPE html>
<html>
  
<body>
    <div
        id="element"
        data-typeId="123"
        data-name="name"
        data-points="10"
        data-important="true">
        This is the Target Element.
    </div>

    <br />
    <button onclick="myFunction()">
      	Get Attributes
  	</button>
    
  	<p id="result"></p>

    <script>
        let result = document.getElementById("result");
        let e = document.getElementById("element");

        function myFunction() {
            let jsonData = JSON.stringify({
                id: parseInt(e.dataset.typeid),
                points: parseInt(e.dataset.points),
                important: e.dataset.important,
                dataName: e.dataset.name
            });
            result.innerHTML = jsonData;
        }
    </script>
</body>
  
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 12. click to get attributes for target element ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image012.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>

<!-- image012.gif -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2. Using getAttribute() Method</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The getAttribute() method in JavaScript retrieves the value of a specified attribute from an HTML element. To get data attributes, use element.getAttribute(‘data-attribute’). This method allows precise selection and manipulation of individual data attributes without accessing all at once.

```
<!DOCTYPE html>
<html>
  
<body>
    <div
        id="target"
        data-typeId="123"
        data-name="name"
        data-points="10"
        data-important="true"
    >
        This is the Target Element.
    </div>

    <br />
    <button onclick="myFunction()">Get Attributes</button>
    <p id="result"></p>

    <script>
        let result = document.getElementById("result");
        let e = document.getElementById("target");

        function myFunction() {
            let jsonData = JSON.stringify({
                id: parseInt(e.getAttribute('data-typeId')),
                points: parseInt(e.getAttribute('data-points')),
                important: e.getAttribute('data-important'),
                dataName: e.getAttribute('data-name')
            });
            result.innerHTML = jsonData;
        }
    </script>
</body>
  
</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 13. click to get attributes ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image013.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image013.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-06">06. How To Get Element By Class Name In JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
When working with the DOM in JavaScript, selecting elements by their class names is a common task. JavaScript provides several methods to achieve this, whether we need to select one or multiple elements. In this article, we will cover different approaches to get elements by class name in JavaScript.

<h4>Prerequisites</h4>
  - HTML
  - CSS
  - JavaScript

Below are the following approaches to get elements by class name in Javascript:

<h4>Table of Content</h4>

  - Using document.getElementsByClassName()
  - Using document.querySelector()
  - Using document.querySelectorAll()

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1. Using document.getElementsByClassName()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In this approach we are using the document.getElementsByClassName() method. This method selects all elements with a specific class name and returns a live HTMLCollection. Think of it as a way to collect all elements with same label. In this, list gets updated automatically if elements are added or removed.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Syntax:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre><code>var elements = document.getElementsByClassName("className");</code></pre>

<h4>Example: In this example we are using the getElementsByClassName() method to get element by class name in javascript.</h4>

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
     content="width=device-width,
      initial-scale=1.0">
    <title>Get Elements by Class Name</title>
    <style>
        .output {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            background-color: #f9f9f9;
        }
    </style>
</head>

<body>
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>

    <div class="output" id="output1"></div>

    <script>
        var boxes =
         document.getElementsByClassName("box");
        var output =
         document.getElementById("output1");
        output.innerHTML = 
        "Number of boxes: " + boxes.length;
    </script>
</body>

</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 14. get elements by class name ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image014.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image014.png -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>2. Using document.querySelector()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In this approach we are using the document.querySelector() method. This method returns the first element that matches the specified selector (class name). It is useful when you only need to select a single element by class name.

Syntax:

<pre>var element = document.querySelector(".className");</pre>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: In this example we are using the querySelector() method to get element by class name and we will change the background color of selected class in javascript.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
     content="width=device-width,'' initial-scale=1.0">
    <title>Query Selector Example</title>
    <style>
        .box {
            padding: 10px;
            margin: 5px;
            border: 1px solid #ccc;
        }
    </style>
</head>

<body>
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>

    <script>
        var firstBox = 
        document.querySelector(".box");
        firstBox.style.backgroundColor =
         "lightblue"; // Change the background color to light blue
        firstBox.style.color = "white"; // Change the text color to white
    </script>
</body>

</html>
```

<h4>Output</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 15. query selector example ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image015.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image015.png -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3. Using document.querySelectorAll()</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In this approach we are using the document.querySelectorAll() method. This method finds all elements that match a specific CSS selector, like class name. It gives you a static list, which means it wont automatically update if page changes.

Syntax:

```
var elements = document.querySelectorAll(".className");
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: In below example we are using the querySelectorAll and we will print all the content which have that class name.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
     content="width=device-width,
      initial-scale=1.0">
    <title>Query Selector All Example</title>
    <style>
        .output {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            background-color: #f9f9f9;
        }
    </style>
</head>

<body>
    <div class="box">Box 1</div>
    <div class="box">Box 2</div>
    <div class="box">Box 3</div>

    <div class="output" id="output3"></div>

    <script>
        var allBoxes = 
        document.querySelectorAll(".box");
        var output = 
        document.getElementById("output3");
        var content = "Contents of all boxes: <br>";
        allBoxes.forEach(function (box) {
            content += box.innerText + "<br>";
        });
        output.innerHTML = content;
    </script>
</body>

</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 16. query selector all example ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image016.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image016.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-07">07. How to Get Value by Class Name using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This article will show you how to use JavaScript to get value by class name. To get the value 
of an element by its class name in JavaScript, you can use the getElementsByClassName() method. 
This method returns an array-like object of all elements with the specified class name. You can 
then access the value property of the first element in the array to get the value.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example: In this example, we will get the classname of an element.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
        
    <title>Get Value by Class Name</title>
</head>

<body style="text-align: center;">
    <h1 class="heading">
        GeeksforGeeks
    </h1>

    <p class="para">
        A computer science portal for geeks
    </p>
    
    <button onclick="myGeeks()">
        Get Value
    </button>

    <p id="result"></p>

    <script>
        function myGeeks() {

            // Get elements with the class name 'heading'
            let headingElements = 
                document.getElementsByClassName('heading');

            // Check if any elements with the 
            // specified class name exist
            if (headingElements.length > 0) {

                // Access the value of the first 
                // element in the collection
                let headingVal = headingElements[0].innerHTML;

                // Update the content of the 'result' element
                document.getElementById('result')
                    .innerHTML = headingVal;
            } else {
                console.log(
                  'Element with class name "heading" not found.');
            }
        }
    </script>
</body>

</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 17. query selector all example ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image017.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>


<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Example 2: In this example, we will get the second element by class name.</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <title>Get Value by Class Name</title>
</head>

<body style="text-align: center;">
    <h1 class="heading text">
        GeeksforGeeks
    </h1>

    <p class="para text">
        A computer science portal for geeks
    </p>
    
    <button onclick="myGeeks()">
        Get Value
    </button>

    <p id="result"></p>

    <script>
        function myGeeks() {

            // Get elements with the class name 'heading'
            let headingElements = 
                document.getElementsByClassName('text');

            // Check if any elements with the 
            // specified class name exist
            if (headingElements.length > 0) {

                // Access the value of the first 
                // element in the collection
                let headingVal = headingElements[1].innerHTML;

                // Update the content of the 'result' element
                document.getElementById('result')
                    .innerHTML = headingVal;
            } else {
                console.log(
                  'Element with class name "text" not found.');
            }
        }
    </script>
</body>

</html>
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 18. query selector all example ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image018.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-08">08. How to Get Domain Name From URL in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In JavaScript, the URL object allows you to easily parse URLs and access their components. This is useful when you need to extract specific parts of a URL, such as the domain name. The hostname property of the URL object provides the domain name of the URL.

<h4>Prerequisite</h4>
  - Javascript
  - HTML

Below are the following approaches to get a domain name from a URL in Javascript:

<h4>Table of Content</h4>
  - Using the URL Object
  - Using Regular Expressions

<h3>Using the URL Object</h3>
The new URL(url) constructor parses the URL and creates a URL object. This object has various properties that represent different parts of the URL. The hostname property of the URL object returns the domain name. For instance, for the URL https://www.example.com/path/to/resource?query=param, urlObject.hostname would return www.example.com. If the URL is invalid, the URL constructor will throw an error. In the catch block, you can handle this error, for example by logging it or returning a default value.

<h4>Example: This example shows the extraction of the domain name from a URL.</h4>


<!DOCTYPE html>
<html lang="en">

```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>How to get domain name from URL in JavaScript</h1>
    <p>Domain Name : <span id="span"></span></p>
    <script src="Index.js"> </script>
</body>
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 33.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image033.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image033.png -->

<h3>Using Regular Expressions</h3>
If you want more control or need to support environments where the URL object is not available, you can use regular expressions to extract the domain from the URL string.

<h4>Example: This example demonstrates the extraction of the domain name using Regex.</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>How to get domain name from URL in JavaScript</h1>
    <p>Domain Name : <span id="span"></span></p>
    <script src="Index.js"> </script>
</body>
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 34.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image034.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image034.png -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-09">09. How to get protocol, domain and port from URL using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The protocol, domain, and port of the current page can be found by two methods:

<h4>Method 1: Using location.protocol, location.hostname, location.port methods: The location interface has various methods that can be used to return the required properties.</h4>

  - The location.protocol property is used to return the protocol scheme of the URL along with the final colon(:).
  - The location.hostname is used to return the domain name of the URL.
  - The location.port property is used to return the port of the URL. It returns nothing if the port is not described explicitly in the URL.

<h4>Syntax:</h4>

```
protocol = location.protocol;
domain = location.hostname;
port = location.port;
```

<h4>Example:</h4>

```
<!DOCTYPE html> 
<html> 
  
<head> 
    <title> 
        Get protocol, domain, and port from URL 
    </title> 
</head> 
  
<body> 
    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1> 
      
    <b> 
        Get protocol, domain, and port from URL 
    </b> 
      
    <p> 
        Protocol is:  
        <span class="protocol"></span> 
    </p> 
      
    <p> 
        Domain is:  
        <span class="domain"></span> 
    </p> 
      
    <p> 
        Port is:  
        <span class="port"></span> 
    </p> 
      
    <button onclick="getDetails()"> 
        Get protocol, domain, port 
    </button> 
      
    <script type="text/javascript"> 
        function getDetails() { 
            protocol = location.protocol; 
            domain = location.hostname; 
            port = location.port; 
  
            document.querySelector('.protocol').textContent 
                    = protocol; 
            document.querySelector('.domain').textContent 
                    = domain; 
            document.querySelector('.port').textContent 
                    = port; 
        } 
    </script> 
</body> 
  
</html>          
```

<h4>Output:</h4>
  - Before Clicking the button:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 35.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image035.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image035.png -->

  - After Clicking the button:
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 36.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image036.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p><!-- image036.png -->

<h4>Method 2: Using the URL interface: The URL interface is used to represent object URL. It can be used for getting the port, domain, and protocol as it has inbuilt methods to get these values.</h4>

  - The url.protocol property is used to return the protocol scheme of the URL along with the final colon(:).
  - The url.hostname is used to return the domain of the URL.
  - The url.port property is used to return the port of the URL. It returns ” if the port is not described explicitly.

Note: This API is not supported in Internet Explorer 11.

<h4>Syntax:</h4>

```
current_url = window.location.href;
url_object = new URL(current_url);

protocol = url_object.protocol;
domain = url_object.hostname;
port = url_object.port;
```

<h4>Example:</h4>

```
<!DOCTYPE html> 
<html> 
      
<head> 
    <title> 
        Get protocol, domain, and port from URL 
    </title> 
</head> 
  
<body> 
    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1> 
      
    <b> 
        Get protocol, domain, and port from URL 
    </b> 
      
    <p>Protocol is: <span class="protocol"></span></p> 
    <p>Domain is: <span class="domain"></span></p> 
    <p>Port is: <span class="port"></span></p> 
      
    <button onclick="getDetails()"> 
        Get protocol, domain, port 
    </button> 
      
    <script type="text/javascript"> 
        function getDetails() { 
            current_url = window.location.href; 
            url_object = new URL(current_url); 
  
            protocol = url_object.protocol; 
            domain = url_object.hostname; 
            port = url_object.port; 
  
            document.querySelector('.protocol').textContent 
                    = protocol; 
            document.querySelector('.domain').textContent 
                    = domain; 
            document.querySelector('.port').textContent 
                    = port; 
        } 
    </script> 
</body> 
  
</html>                     
```

<h4>Output:</h4>
  - Before Clicking the button:
  
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 37.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image037.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p><!-- image037.png -->

  - After Clicking the button:
  
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 38.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image038.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image038.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-10">10. How to Extract the Host Name from URL using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Extracting the hostname from a URL using JavaScript means retrieving the domain part from a complete web address. This can be done using JavaScript’s URL object or methods like window.location, which allow easy access to the hostname of a URL.

<h3>What is URL?</h3>
A URL (Uniform Resource Locator) is the web address used to access resources on the internet, such as webpages, images, or files, through browsers.

<h3>Using the hostname property of the current window location</h3>
Here we are using JavaScript’s window.location object to extract the full URL and hostname. The window.location.href outputs the current page URL, while window.location.hostname retrieves only the domain part (hostname) of that URL.

<h4>Syntax</h3>
<pre>window.location.propertyname</pre>

<h4>Example : In this example, we will use the self URL, where the code will run to extract the hostname.</h4>

```
<!DOCTYPE html>
<html>

<head>
    <title>
        Get domain from URL
    </title>
</head>

<body>
    <h1 style="color: green">
        GeeksforGeeks
    </h1>

    <b>URL is:</b>

    <script>
        document.write(window.location.href);
    </script>

    <br>
    <b>hostname is:</b>

    <script>
        document.write(window.location.hostname);
    </script>
</body>

</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 39.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image039.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image039.png -->

<h3>Extracting Hostname Using indexOf and Looping</h3>
here we extracts the hostname from a user-provided URL by locating the position of “://” using indexOf(). It then loops through characters starting after “://” until it encounters a “/”, constructing and displaying the extracted hostname on the page.

<h4>Syntax</h4>
<pre>url3.indexOf("://");</pre>

<h4>Example : In this example, we will ask for the URL to the user and then will perform the extraction of the hostname on that URL.</h4>

```
<!DOCTYPE html>
<html>

<head>
    <title>Extracting URL</title>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>
    <b>Extracting URL</b>
    <br><br>
    <form name="f1">
        <input type="text" name="txt" placeholder="Paste URL" />
        <input type="button" value="click" onclick="url2()" />
    </form>
    <script>
        function url2() {

            let url3 = document.f1.txt.value;

            let j = url3.indexOf("://");

            let host = "";

            for (i = j + 3; i < url3.length; i++) {
                if (url3.charAt(i) != '/') {
                    host = host + "" + url3.charAt(i);
                } else {
                    break;
                }
            }
            document.write(host);
        }
    </script>
</body>

</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 40.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image040.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image040.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-11">11. How to Get the Current URL using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Here are two different methods to get the current URL in JavaScript.

<h3>1. Using Document.URL Property</h3>
The DOM URL property in HTML is used to return a string that contains the complete URL of the current document. The string also includes the HTTP protocol such as ( http://).

<h4>Syntax</h4>

<pre>document.URL</pre>

<h4>Return Value: It returns a string value that represents the full URL of the document.</h4>

```
<script>
// Get the current URL using document.URL
let currentUrl = document.URL;

// Log the URL to the console
console.log(currentUrl);
</script>
```

<h4>Output</h4>
<pre>http://127.0.0.1:5500/index.html</pre>


<h3>2. Using window.location.href Property</h3>
The window.location.href property of the HTML DOM Window object returns a string containing the URL of the current page. This property is part of the Location object, which contains information about the current location of the document.

<h4>Syntax</h4>
<pre>window.location.href</pre>

```
<script>
// Get the current URL using document.URL
let currentUrl = document.URL;

// Log the URL to the console
console.log(currentUrl);
</script>
```

<h4>Output:</h4>
<pre>http://127.0.0.1:5500/index.html</pre>

Note: Use the HTML file to copy paste and run the given code and you can see the output in the console, it will print the URL.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-12">12. How to get URL Parameters using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
To get URL parameters using JavaScript means extracting the query string values from a URL. URL parameters, found after the ? in a URL, pass data like search terms or user information. JavaScript can parse these parameters, allowing you to programmatically access or manipulate their values.

For getting the URL parameters, there are 2 ways:

<h4>Table of Content</h4>
  - Using the URLSearchParams Object
  - Separating and accessing each parameter pair

<h3>Method 1: Using the URLSearchParams Object</h3>
The URLSearchParams interface provides methods to work with URL parameters. After splitting the URL with ?, the parameters part is passed to URLSearchParams(). Using entries(), you retrieve key/value pairs, allowing access to all URL parameters for further use.

<h4>Syntax:</h4>

```
let paramString = urlString.split('?')[1];
let queryString = new URLSearchParams(paramString);
for (let pair of queryString.entries()) {
   console.log("Key is: " + pair[0]);
   console.log("Value is: " + pair[1]);
}
```

<h4>Example: In this example we retrieves URL parameters using JavaScript. It splits the URL, extracts parameters with URLSearchParams(), and logs each key-value pair to the console when the button is clicked.</h4>

```
<!DOCTYPE html>
<html>
<head>
    <title>
          How To Get URL Parameters using JavaScript?
      </title>
</head>

<body>
    <h1 style="color:green;">
        GeeksforGeeks
    </h1> 
    <b>
        How To Get URL Parameters
        With JavaScript?
    </b>
    <p> The url used is: 
https://www.example.com/login.php?a=GeeksforGeeks&b=500&c=Hello Geeks 
    </p>

    <p> 
       Click on the button to get the url 
       parameters in the console. 
    </p>

    <button onclick="getParameters()"> Get URL parameters </button>
    <script>
    function getParameters() {
        let urlString = 
"https://www.example.com/login.php?a=GeeksforGeeks&b=500&c=Hello Geeks";
        let paramString = urlString.split('?')[1];
        let queryString = new URLSearchParams(paramString);
        for(let pair of queryString.entries()) {
            console.log("Key is:" + pair[0]);
            console.log("Value is:" + pair[1]);
        }
    }
    </script>
</body>
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 41.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image041.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image041.gif -->

<h3>Method 2: Separating and accessing each parameter pair</h3>
The URL’s query string is split at ? to isolate parameters. Using split(“&”) divides parameters into an array. Looping through this array, each key-value pair is split by =, giving keys at the first index and values at the second, enabling parameter extraction.

<h4>Syntax:</h4>

```
let paramString = urlString.split('?')[1];
let params_arr = paramString.split('&');
for (let i = 0; i < params_arr.length; i++) {
   let pair = params_arr[i].split('=');
   console.log("Key is:", pair[0]);
   console.log("Value is:", pair[1]);
}
```

<h4>Example: In this example we retrieves URL parameters by splitting the URL string manually. It extracts each key-value pair, splits them, and logs the results in the console when the button is clicked.</h4>

```
<!DOCTYPE html>
<html>
<head>
    <title> 
          How To Get URL Parameters using JavaScript? 
      </title>
</head>

<body>
    <h1 style="color:green;">
        GeeksforGeeks
    </h1> <b>
        How To Get URL Parameters
        With JavaScript?
    </b>
    <p> The url used is: 
https://www.example.com/login.php?a=GeeksforGeeks&b=500&c=Hello Geeks 
    </p>

    <p> 
       Click on the button to get the url
       parameters in the console. 
    </p>

    <button onclick="getParameters()"> Get URL parameters </button>
    <script>
    function getParameters() {
        let urlString = 
"https://www.example.com/login.php?a=GeeksforGeeks&b=500&c=Hello Geeks";
        let paramString = urlString.split('?')[1];
        let params_arr = paramString.split('&');
        for(let i = 0; i < params_arr.length; i++) {
            let pair = params_arr[i].split('=');
            console.log("Key is:" + pair[0]);
            console.log("Value is:" + pair[1]);
        }
    }
    </script>
</body>
  
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 42.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image042.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image042.gif -->


<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-13">13. How to parse URL using JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Given an URL and the task is to parse that URL and retrieve all the related data using JavaScript. Example:

```
URL: https://www.geeksforgeeks.org/courses
When we parse the above URL then we can find
hostname: geeksforgeeks.com
path: /courses
```

<h4>Method 1: In this method, we will use createElement() method to create a HTML element, anchor tag and then use it for parsing the given URL.</h4>

```javascript
// Store the URL into variable 
var url = "https://geeksforgeeks.org/pathname/?search=query"; 
      
// Created a parser using createElement() method 
var parser = document.createElement("a"); 
parser.href = url; 
      
// Host of the URL 
console.log(parser.host); 
      
// Hostname of the URL 
console.log(parser.hostname ); 
      
// Pathname of URL 
console.log(parser.pathname); 
      
// Search in the URL 
console.log(parser.search );
```

<h4>Output:</h4>

```
geeksforgeeks.org
geeksforgeeks.org
/pathname/
?search=query
```

<h4>Method 2: In this method we will use URL() to create a new URL object and then use it for parsing the provided URL.</h4>

```javascript
// Store the URL into variable 
var url = 
"https://geeksforgeeks.org:3000/pathname/?search=query"; 
      
// Created a URL object using URL() method 
var parser = new URL(url); 
      
// Protocol used in URL 
console.log(parser.protocol); 
      
// Host of the URL 
console.log(parser.host); 
      
// Port in the URL 
console.log(parser.port); 
      
// Hostname of the URL 
console.log(parser.hostname); 
      
// Search in the URL 
console.log(parser.search); 
      
// Search parameter in the URL 
console.log(parser.searchParams);
```

<h4>Output:</h4>

```
https:
geeksforgeeks.org:3000
3000
geeksforgeeks.org
?search=query
search=query
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-14">14. Manipulating HTML Elements with JavaScript</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
JavaScript is a powerful language that can be used to manipulate the HTML elements on a web page. By using JavaScript, we can access the HTML elements and modify their attributes, styles, and content. This allows us to create dynamic and interactive web pages.

Methods to Identify the elements to manipulate: There are several methods to identify the HTML elements that we want to manipulate using JavaScript. The most common methods are:

  - Using the element's ID: We can assign an ID to an HTML element and use document.getElementById() to access it.
  - Using the element's class name: We can assign a class name to an HTML element and use document.getElementsByClassName() to access it.
  - Using the element's tag name: We can use document.getElementsByTagName() to access all elements with a particular tag name.

Accessing the properties of the elements: Once we have identified the HTML element that we want to manipulate, we can access its properties using JavaScript. For example, to access the text content of an element, we can use the innerHTML property. Similarly, we can access the style properties of an element using the style property.

Use Event Listeners to Respond to User Interactions: We can use event listeners to respond to user interactions such as clicking a button or hovering over an element. Event listeners are functions that are executed when a particular event occurs. For example, we can use the onclick event listener to execute a function when a button is clicked.

When building a website or web application, it's common to need to access and manipulate HTML elements using JavaScript. There are several methods available in JavaScript that allow you to do this, including getElementById(), getElementsByClassName(), and getElementsByTagName(). In this article, we'll take a systematic approach to use these methods and show you how to access and manipulate elements in your HTML documents.

<h4>Step 1: Identify the Element You Want to Manipulate:</h4>
The first step in working with HTML elements in JavaScript is to identify the element you want to manipulate. There are several ways to do this, depending on the specific element you're trying to access. Here are some common methods:

  - getElementById() Method: Use this method to access an element with a specific ID. IDs should be unique within an HTML document, so this method will always return a single element.
  - getElementsByClassName() Method: Use this method to access all elements with a specific class name. Multiple elements can have the same class name, so this method will return a collection of elements.
  - getElementsByTagName() Method: Use this method to access all elements with a specific tag name. Multiple elements can have the same tag name, so this method will also return a collection of elements.

<h4>Syntax:</h4>

```
let element = document.getElementById("my-id");
let elements = document.getElementsByClassName("myClass");
let elements = document.getElementsByTagName("p");
```

<h4>Step 2: Access the Element's Properties and Methods:</h4>
Once you've identified the element you want to manipulate, you can access its properties and methods. Properties are values that describe the state of an element, such as its innerHTML, value, or src attributes. Methods are functions that allow you to manipulate an element in some way, such as changing its innerHTML, className, or style properties. Here are some examples of how to access an element's properties and methods:

```
// Accessing an element's methods
element.innerHTML = "New content!"; // changes the content of the element
element.classList.add("newClass"); // adds a new CSS class to the element
element.style.backgroundColor = "red"; // changes the background color of the element
```

<h4>Step 3: Use Event Listeners to Respond to User Interactions:</h4>
In addition to manipulating elements directly, you can also use JavaScript to respond to user interactions, such as clicks, mouse movements, or keyboard inputs. To do this, you can use event listeners, which are functions that are triggered when a specific event occurs on an element. Here's an example of how to add an event listener to a button element:

```
<button id="myButton">Click me!</button>
<script>
let button = document.getElementById("myButton");
button.addEventListener("click", function() {
     console.log("Button clicked!");
});
</script>
```

In this example, we use getElementById() to access a button element with the ID "myButton". We then add an event listener to the button using the addEventListener() method. The event we're listening for is a "click" event, which is triggered when the user clicks the button. When the event is triggered, the function we passed as the second argument is executed, which logs a message to the console.

<h4>Example 1. Id selector</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>document.getElementById()</title>
</head>

<body>
    <h1 id="my-id">Hello World!</h1>

    <script>
        // Get element with id "my-id"
        var elements = document.getElementById("my-id");
        
        // Change the content of the element
        elements.innerHTML = "New content!";
    </script>

</body>
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 43.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image043.jpg?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image043.jpg -->


<h4>Example 2. Class Selector:</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>document.getElementsByClassName()</title>
</head>

<body>
    <p class="myClass">This is a paragraph.</p>
    <p class="myClass">This is another paragraph.</p>

    <script>
        // Get all elements with class "myClass"
        var elements = document.getElementsByClassName("myClass");
        
        // Change the content of the first element
        elements[0].innerHTML = "New content!";
    </script>

</body>
</html>
```

<h4>Output</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 44.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image044.jpg?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image044.jpg -->

<h4>Example 3: Here is an example of how to manipulate an HTML element using JavaScript:</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>DOM Manipulation</title>
</head>

<body>
    <h1 id="my-heading">Hello, World!</h1>

    <button id="my-button">Click me!</button>

    <script>
        const heading = document.getElementById("my-heading");
        const button = document.getElementById("my-button");
        button.addEventListener("click", function () {
            heading.innerHTML = "Button clicked";
            heading.style.color = "red";
        });
    </script>
</body>
</html>
```

Explanation: In this example, we first access the button element using the getElementById() method. We then add an event listener to the button using the addEventListener() method. The event we are listening for is the "click" event, and the function we want to execute when the event occurs is defined inline.

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 45.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image045.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image045.gif -->

Conclusion: In conclusion, manipulating HTML elements with JavaScript is a powerful technique that can be used to create dynamic and interactive web pages. By using the methods discussed above, we can identify and access the HTML elements on a web page and modify their properties to create the desired behavior.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-15">15. How to use innerHTML in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The innerHTML property in JavaScript allows you to get or set the HTML content of an element as a string.

<h4>Syntax For</h4>

<h4>Getting HTML content of an element:</h4>

```
let element = document.getElementById("myElementId");
let htmlContent = element.innerHTML;
```

<h4>Setting HTML content of an element:</h4>

```
let element = document.getElementById("myElementId");
element.innerHTML = "New HTML content";
```

<h3>Here are step-by-step instructions on how to use the innerHTML property in JavaScript</h3>

<h4>Step 1: Access an HTML element</h4>
Use JavaScript to select the HTML element you want to manipulate. You can do this using various methods like document.getElementById(), document.querySelector(), or document.querySelectorAll().

```
<div id="myElement">Initial content</div>
let element = document.getElementById("myElement");
```

<h4>Step 2: Get the HTML content</h4>
If you want to retrieve the current HTML content of the element, use the innerHTML property.

```
let htmlContent = element.innerHTML;
console.log(htmlContent); 
// Output: Initial content
```

<h4>Step 3: Set the HTML content</h4>
If you want to replace or update the HTML content of the element, assign a new HTML string to the innerHTML property.

```
element.innerHTML = "<b>New content</b>";
```

<h4>Step 4: Verify the changes(optional)</h4>
You can optionally verify that the HTML content has been updated as expected by accessing the element again or using browser developer tools.

```
console.log(element.innerHTML);
 // Output: <b>New content</b>
```

<h4>Example: Here, we have show the code on how to use innerHTML in JavaScript.</h4>

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,
                                   initial-scale=1.0">
    <title>innerHTML Example</title>
    <style>
        .container {
            padding: 10px;
        }
    </style>
</head>

<body>
    <div class="container" id="myElement">Initial content</div>
    <button onclick="changeContent()">Change Content</button>

    <script>
        function changeContent() {
            let element = document.getElementById("myElement");
            element.innerHTML = "<b>New content</b>";
        }
    </script>
</body>

</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 46.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image046.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image046.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2 id="#D-16">16. JavaScript innerHTML</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

The innerHTML property in JavScript is used to append the dynamic HTML or text content to an element using JavaScript. It is designed to add dynamic HTML, but developers also use it to add text content as well. It can be directly used with the element by selecting it using DOM manipulation.

<h4>Syntax:</h4>
<pre>selctedHTMLElement.innerHTML = "contentToAppend";</pre>

<h4>Example 1: The below code shows a basic implementation of innerHTML property to append HTML directly to an element.</h4>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, 
                                   initial-scale=1.0">
    <title>
        JavaScript innerHTML
    </title>
    <style>
        #container{
            text-align: center;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h2>
            The below content is added dynamically
            using the innerHTML property in JavaScript.
        </h2>
    </div>  
    
    <script>
        const container = document.getElementById('container');
        container.innerHTML += 
        `
            <h3>
                Hey Geek, <br/>
                Welcome to GeeksforGeeks
            </h3>
            <p>
                This content is added using the 
                innerHTML property.
            </p>
        `;
    </script>
</body>
</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 47.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image047.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image047.png -->

<h4>Example 2: The below code implements the innerHTML property with click event to add HTML onclick to the button.</h4>

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, 
                                   initial-scale=1.0">
    <title>
        JavaScript innerHTML
    </title>
    <style>
        #container {
            text-align: center;
        }
    </style>
</head>

<body>
    <div id="container">
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h2>
            Click the below button to dynamically add
            the HTML using the innerHTML property.
        </h2>
        <button id="myBtn">Add HTML</button>
    </div>

    <script>
        const myBtn = document.getElementById('myBtn');
        function clickHandler() {
            const container = 
                document.getElementById('container');
            container.innerHTML +=
                `
                <h3>
                    Hey Geek, <br/>
                    Welcome to GeeksforGeeks
                </h3>
                <p>
                    This content is added using 
                    the innerHTML property.
                </p>
            `;
        }
        myBtn.addEventListener('click', clickHandler);
    </script>
</body>

</html>
```

<h4>Output:</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 48.  ~~~~~~~~~~~~~~~~-->
<p align="center" >
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image048.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</p>
<!-- image048.gif -->










