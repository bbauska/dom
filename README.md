<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ readme.md of dom ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>DOM</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>JavaScript - How to Manipulate DOM Elements?</h2>
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

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 01.  change content using innerHTML ~~~~~~~~~~~~~~~~-->
<div style="text-align: center">
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image001.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
</div>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 02. manipulate class ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image002.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a><!-- image002.gif -->
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
<h2>How to Add a <b><mark>Class</mark></b> to <b><mark>DOM Element</mark></b> in JavaScript?</h2>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 03. manipulate class ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image003.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image003.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using <b><mark>className</mark></b> Property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
In this approach, we are using the <b><mark>clasName</mark></b> property. This property returns the 
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 04.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image004.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image004.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>How to select DOM Elements in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Selecting <b><mark>DOM (Document Object Model)</mark></b> elements is a fundamental aspect of web 
development with JavaScript. It allows developers to interact with and manipulate elements 
on a webpage dynamically. Proper selection of elements is crucial for tasks such as updating 
content, adding event listeners, or modifying styles.

Below are the approaches to select DOM elements in JavaScript:

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>Table of Content</h4>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<ul>
  <li>Using <b><mark>getElementById</mark></b></li>
  <li>Using <b><mark>getElementsByClassName</mark></b></li>
  <li>Using <b><mark>getElementsByTagName</mark></b></li>
  <li>Using <b><mark>querySelector</mark></b></li>
  <li>Using <b><mark>querySelectorAll</mark></b></li>
</ul>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using <b><mark>getElementById</mark></b></h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This method selects a single element by its unique ID attribute.

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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 05.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image005.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image005.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using <b><mark>getElementsByClassName</mark></b></h3>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 06.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image006.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image006.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using <b><mark>getElementsByTagName</mark></b></h3>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 07.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image007.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image007.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using querySelector</h3>
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

<h4>Output:</h4.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 08.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image008.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image008.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using querySelectorAll</h3>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 09.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image009.png?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image009.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>How to get all ID of the DOM elements with JavaScript?</h2>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 10.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image010.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
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
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~ 11.  ~~~~~~~~~~~~~~~~-->
<a href="" 
  target="_blank" rel="noopener noreferrer">
  <img class="displayed"
    src="./images/image011.gif?raw=true"
    loading="lazy"
    style="width:40%;"
    title=""
    alt="." />
</a>
<!-- image011.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>JavaScript – How to Get the Data Attributes of an Element?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->





