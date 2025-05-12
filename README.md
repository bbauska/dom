<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h1>DOM</h1>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>JavaScript - How to Manipulate DOM Elements?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <b><mark>DOM</mark></b> stands for the <b><mark>Document Object Model (DOM)</mark></b>, which 
allows us to interact with the document and change its structure, style, and content. We can use 
the DOM to change the content and style of an HTML element by changing its properties.</p>

<h2>How to Manipulate DOM Elements?</h2>
<p>We can manipulate or change the DOM elements by using the following methods:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>1. Change the Content of an Element</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>You can change the content inside an HTML element using JavaScript. The two most common 
properties for this are innerHTML and textContent:</p>
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

<!-- image001.gif -->

<h4>In this example</h4>

  - <b><mark>innerHTML</mark></b> changes the entire content of an element, including HTML tags. In this case, we replace the content of the first <b><mark>div</mark></b> with bold text using <strong>.
  - <b><mark>textContent</mark></b> changes only the text inside the element, ignoring any HTML tags. The second <b><mark>div</mark></b> is updated with plain text, without any HTML formatting.
  - The first <b><mark>div</mark></b> shows "This is the original content using <b><mark>innerHTML</mark></b>."
  - The second <b><mark>div</mark></b> shows "This is the original text content using <b><mark>textContent</mark></b>."
  - After clicking the "Change Content" button.
  - The first <b><mark>div</mark></b> will display "This is changed using <b><mark>innerHTML</mark></b>!" with bold text.
  - The second <b><mark>div</mark></b> will display "This is changed using <b><mark>textContent</mark></b>!" with plain text.


<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
2. Manipulate the Class Attribute
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can add, remove, or toggle classes on an element using JavaScript. This is helpful for styling or applying animations.

  * classList.add(): Adds a class to an element.
  * classList.remove(): Removes a class from an element.
  * classList.toggle(): Toggles a class (adds it if it's not present, removes it if it is).

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

<h4>Output:</h4>
<!-- image002.gif -->
<h4>In this example</h4>

  - Adding a Class (addClass()): When you click the "Add 'highlight' Class" button, the highlight class is added to the div element with the id="example". This changes the text color to red and makes it bold (as defined in the CSS).
  - Removing a Class (removeClass()): When you click the "Remove 'bold' Class" button, the bold class is removed from the div, which removes the bold styling from the text.
  - Toggling a Class (toggleClass()): When you click the "Toggle 'highlight' Class" button, the highlight class is either added or removed, depending on whether it's already present. If the class is present, it will be removed; if not, it will be added.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>3. Set CSS Styles Using JavaScript</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can directly manipulate the CSS styles of an element using the style property. This allows you to dynamically change how elements appear on the page.

```
// Changing multiple CSS properties
document.getElementById("demo").style.color = "red";
document.getElementById("demo").style.fontSize = "20px";
// Adding more than one style
document.getElementById("demo").style.cssText = "color: blue; font-size: 18px;";
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>4. Create, Add, and Remove Elements</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Sometimes, you need to create new elements, add them to the DOM, or remove existing ones. You can do this easily with the following methods

  - document.createElement(): Creates a new element.
  - appendChild(): Adds a new element to a parent element.
  - removeChild(): Removes a child element from a parent.

```
// Create a new element
let newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";
// Add the new element to the DOM
document.body.appendChild(newDiv);
// Remove an element from the DOM
document.body.removeChild(newDiv);
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
5. Insert Elements at a Specific Position
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can insert new elements at specific positions relative to existing elements using methods like insertBefore().

```
// Create a new element
let newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";

// Find an existing element to insert before
let referenceNode = document.getElementById("referenceElement");

// Insert the new element before the reference element
document.body.insertBefore(newDiv, referenceNode);
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>6. Manipulate Element Attributes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
You can easily get, set, or remove the attributes of an HTML element using the following methods:

  - getAttribute(): Retrieves the value of an attribute.
  - setAttribute(): Sets a new value for an attribute.
  - removeAttribute(): Removes an attribute.

```
// Get the value of an attribute
let src = document.getElementById("image").getAttribute("src");

// Set a new value for an attribute
document.getElementById("image").setAttribute("src", "new-image.jpg");

// Remove an attribute
document.getElementById("image").removeAttribute("src");
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>7. Manipulate Data Attributes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
HTML5 introduced data attributes, which are custom attributes that you can use to store extra information about an element. These are particularly useful for adding data to an element without affecting its visual structure.

  - dataset: A special property in JavaScript that allows you to access data attributes.

```
// Setting a data attribute
document.getElementById("demo").dataset.userId = "12345";
// Getting a data attribute
let userId = document.getElementById("demo").dataset.userId;
console.log(userId); // Outputs: 12345
```

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>How to Add a Class to DOM Element in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Adding a class to a DOM (Document Object Model) element in JavaScript is a fundamental task that enables developers to dynamically manipulate the appearance and behavior of web pages. Classes in HTML provide a powerful way to apply CSS styles or JavaScript functionality to multiple elements at once.

By using JavaScript, you can easily add, remove, or toggle classes on elements, making your web applications more interactive and responsive to user actions.

These are the following approaches:

<h4>Table of Content</h4>

  - Using classList Property
  - Using className Property
  - Using classList Property

<p>In this approach, we are using classList property to add the class into the DOM element. It 
returns the class name as a DOMTokenList object. It has a method called “add” which is used to 
add class name to elements. we will access the div using the getElementById and we will use the 
add property of classList to add a class.</p>

<h4>Syntax:</h4>

```
element.classList.add("className")
```

<h4>Example: This example shows the implementation of the above-explained approach.</h4>

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

<h4>Output:</h4>
<!-- image003.gif -->

<h3>Using className Property</h3>
In this approach, we are using the clasName property. This property returns the className of the element. If the element has already a class then it will simply add another one to it or else it will append our new class to it.

<h4>Syntax:</h4>

<pre>HTMLElementObject.className</pre>

<h4>Example: This example shows the implementation of the above-explained approach.</h4>

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

<h4>Output:</h4>
<!-- image004.gif -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>How to select DOM Elements in JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Selecting DOM (Document Object Model) elements is a fundamental aspect of web development with JavaScript. It allows developers to interact with and manipulate elements on a webpage dynamically. Proper selection of elements is crucial for tasks such as updating content, adding event listeners, or modifying styles.

Below are the approaches to select DOM elements in JavaScript:

<h4>Table of Content</h4>

  - Using getElementById
  - Using getElementsByClassName
  - Using getElementsByTagName
  - Using querySelector
  - Using querySelectorAll

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using getElementById</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This method selects a single element by its unique ID attribute.

<h4>Syntax:</h4>
<pre>document.getElementById('id')</pre>

<h4>Example:</h4>

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

<h4>Output:</h4>
<!-- image005.png -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using getElementsByClassName</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This method selects elements based on their class attribute. It returns a collection of elements with the specified class name.

<h4>Syntax:</h4>
<pre>document.getElementsByClassName('class')</pre>

<h4>Example:</h4>

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

<h4>Output:</h4>
<!-- image006.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using getElementsByTagName</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This method selects elements based on their tag name. It returns a collection of elements with the specified tag name.

<h4>Syntax:</h4>
<pre>document.getElementsByTagName('tag')</pre>

<h4>Example:</h4>

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

<h4>Output:</h4>
<!-- image007.png -->
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using querySelector</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
This method selects the first element that matches a specified CSS selector. It returns only one element.

<h4>Syntax:</h4>
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
Output:
<!-- image008 -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Using querySelectorAll</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
Similar to querySelector, but it returns a NodeList containing all elements that match the specified CSS selector.

<h4>Syntax:</h4>
<pre>document.querySelectorAll('selector')</pre>
<h4>Example:</h4>

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

<h4>Output:</h4>
<!-- image009.png -->

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>How to get all ID of the DOM elements with JavaScript?</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->



