<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<!-- from: https://javascript.info/basic-dom-node-properties -->
<h2>Node properties: type, tag and contents</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Let’s get a more in-depth look at DOM nodes.</p>

<p>In this chapter we’ll see more into what they are and learn their most used properties.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>DOM node classes</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Different DOM nodes may have different properties. For instance, an element node 
corresponding to tag <mark>&lt;a&gt;</mark> has link-related properties, and the one corresponding 
to <mark>&lt;input&gt;</mark> has input-related properties and so on. Text nodes are not the same as 
element nodes. But there are also common properties and methods between all of them, 
because all classes of DOM nodes form a single hierarchy.</p>

<p>Each DOM node belongs to the corresponding built-in class.</p>

<p>The root of the hierarchy is <span class="node1">EventTarget</span>, that is inherited by 
<span class="node1">Node</span>, and other DOM nodes inherit from it.</p>

<p>Here’s the picture, explanations to follow:</p>

<!-- image here -->

<h3>The classes are:</h3>
<ul>
  <li><a href="">EventTarget</a> – is the root “abstract” class for everything.<br>
    <p>Objects of that class are never created. It serves as a base, so that all DOM nodes support so-called “events”, we’ll study them later.</p>
  </li>
  <li><a href="">Node</a> – is also an “abstract” class, serving as a base for DOM nodes.<br>
    <p>It provides the core tree functionality: <mark>parentNode</mark>, <mark>nextSibling</mark>, 
	<mark>childNodes</mark> and so on (they are getters). Objects of <mark>Node</mark> class 
	are never created. But there are other classes that inherit from it (and so inherit the 
	<mark>Node</mark> functionality).</p>
  </li>
  <li><a href="">Document</a>, for historical reasons often inherited by <mark>HTMLDocument</mark> 
    (though the latest spec doesn’t dictate it) – is a document as a whole.<br>
  The document global object belongs exactly to this class. It serves as an entry point to the DOM.</li>
  <li><a href="">CharacterData</a> – an “abstract” class, inherited by:<br>
    <ul>
      <li><a href="">Text</a> – the class corresponding to a text inside elements, 
	    e.g. <mark>Hello</mark> in <mark>&lt;p&gt;Hello&lt;/p&gt;</mark>.</li>
      <li><a href="">Comment</a> – the class for comments. They are not shown, but each comment becomes a member of DOM.</li>
    </ul>
  </li>
  <li><a href="">Element</a> – is the base class for DOM elements.<br>
    It provides element-level navigation like <mark>nextElementSibling</mark>, 
	<mark>children</mark> and searching methods like <mark>getElementsByTagName</mark>, 
	<mark>querySelector</mark>.<br>
    A browser supports not only HTML, but also XML and SVG. So the Element class serves as a base for more specific classes: SVGElement, XMLElement (we don’t need them here) and HTMLElement.</li>
  </li>Finally, <a href="">HTMLElement</a> is the basic class for all HTML elements. We’ll 
    work with it most of the time.<br>
  <p>It is inherited by concrete HTML elements:</p>
    <ul>
      <li><a href="">HTMLInputElement</a> – the class for <mark>&lt;input&gt;</mark> elements,</li>
      <li><a href="">HTMLBodyElement</a> – the class for <mark>&lt;body&gt;</mark> elements,</li>
      <li><a href="">HTMLAnchorElement</a> – the class for <mark>&lt;a&gt;</mark> elements,</li>
      <li>…and so on.</li>
    </ul>
  </li>
</ul>

<p>There are many other tags with their own classes that may have specific properties and 
methods, while some elements, such as <mark>&lt;span&gt;</mark>, <mark>&lt;section&gt;</mark>, 
<mark>&lt;article&gt;</mark> do not have any specific properties, so they are instances of 
<mark>HTMLElement</mark> class.</p>

<p>So, the full set of properties and methods of a given node comes as the result of the 
chain of inheritance.</p>

<p>For example, let’s consider the DOM object for an <mark>&lt;input&gt;</mark> element. 
It belongs to <mark>HTMLInputElement</mark> class.</p>

<p>It gets properties and methods as a superposition of (listed in inheritance order):</p>

<ul>
  <li><mark>HTMLInputElement</mark> – this class provides input-specific properties,</li>
  <li><mark>HTMLElement</mark> – it provides common HTML element methods (and getters/setters),</li>
  <li><mark>Element</mark> – provides generic element methods,</li>
  <li><mark>Node</mark> – provides common DOM node properties,</li>
  <li><mark>EventTarget</mark> – gives the support for events (to be covered),</li>
  <li>…and finally it inherits from <mark>Object</mark>, so “plain object” methods like
    <mark>hasOwnProperty</mark> are also available.</li>
</ul>

<p>To see the DOM node class name, we can recall that an object usually has the 
<mark>constructor</mark> property. It references the class constructor, and 
<mark>constructor.name</mark> is its name:</p>

<pre>alert( document.body.constructor.name ); // HTMLBodyElement</pre>

<p>…Or we can just <span>toString</span> it:</p>

<pre>alert( document.body ); // &lbrack;object HTMLBodyElement&rbrack;</pre>

<p>We also can use instanceof to check the inheritance:</p>

<pre>
alert( document.body instanceof HTMLBodyElement ); // true
alert( document.body instanceof HTMLElement ); // true
alert( document.body instanceof Element ); // true
alert( document.body instanceof Node ); // true
alert( document.body instanceof EventTarget ); // true
</pre>

<p>As we can see, DOM nodes are regular JavaScript objects. They use prototype-based classes for inheritance.</p>

<p>That’s also easy to see by outputting an element with <mark>console.dir(elem)</mark> 
in a browser. There in the console you can see <mark>HTMLElement.prototype</mark>, 
<mark>Element.prototype</mark> and so on.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>console.dir(elem) versus console.log(elem)</h4>
<p>Most browsers support two commands in their developer tools: <mark>console.log</mark> 
and <mark>console.dir</mark>. They output their arguments to the console. For JavaScript 
objects these commands usually do the same.</p>
<p>But for DOM elements they are different:</p>
<ul>
  <li><mark>console.log(elem)</mark> shows the element DOM tree.</li>
  <li><mark>console.dir(elem)</mark> shows the element as a DOM object, good to explore 
    its properties.</li>
</ul>
<p>Try it on <mark>document.body</mark>.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h4>IDL in the spec</h4>
<p>In the specification, DOM classes aren’t described by using JavaScript, but a special 
<a href="">Interface description language</a> (IDL), that is usually easy to understand.</p>

<p>In IDL all properties are prepended with their types. For instance, <mark>DOMString</mark>, 
<mark>boolean</mark> and so on.</p>

<p>Here’s an excerpt from it, with comments:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
// Define HTMLInputElement
// The colon ":" means that HTMLInputElement inherits from HTMLElement
interface HTMLInputElement: HTMLElement {
  // here go properties and methods of <input> elements

  // "DOMString" means that the value of a property is a string
  attribute DOMString accept;
  attribute DOMString alt;
  attribute DOMString autocomplete;
  attribute DOMString value;

  // boolean value property (true/false)
  attribute boolean autofocus;
  ...
  // now the method: "void" means that the method returns no value
  void select();
  ...
}
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>The “nodeType” property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The nodeType property provides one more, “old-fashioned” way to get the “type” of a DOM node.</p>

<p>It has a numeric value:</p>
<ul>
  <li><mark>elem.nodeType == 1</mark> for element nodes,</li>
  <li><mark>elem.nodeType == 3</mark> for text nodes,</li>
  <li><mark>elem.nodeType == 9</mark> for the document object,</li>
  <li>there are few other values <a href="">in the specification</a>.</li>
</ul>

<p>For instance:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
&lt;body&gt;
  &lt;script&gt;
  let elem = document.body;

  // let's examine: what type of node is in elem?
  alert(elem.nodeType); // 1 =&gt; element

  // and its first child is...
  alert(elem.firstChild.nodeType); // 3 =&gt; text

  // for the document object, the type is 9
  alert( document.nodeType ); // 9
  &lt;/script&gt;
&lt;/body&gt;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<p>In modern scripts, we can use <mark>instanceof</mark> and other class-based tests to 
see the node type, but sometimes <mark>nodeType</mark> may be simpler. We can only read 
nodeType, not change it.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Tag: nodeName and tagName</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Given a DOM node, we can read its tag name from <mark>nodeName</mark> or 
<mark>tagName</mark>  properties:</p>

<p>For instance:</p>

<pre>
alert( document.body.nodeName ); // BODY
alert( document.body.tagName ); // BODY
</pre>

<p>Is there any difference between <span>tagName</span> and <span>nodeName</span>?</p>

<p>Sure, the difference is reflected in their names, but is indeed a bit subtle.</p>

<ul>
  <li>The <mark>tagName</mark> property exists only for <mark>Element</mark> nodes.</li>
  <li>The <mark>nodeName</mark> is defined for any <mark>Node</mark>:
    <ul>
	  <li>for elements it means the same as <mark>tagName</mark>.</li>
	  <li>for other node types (text, comment, etc.) it has a string with the node type.</li>
    </ul>
  </li>
</ul>

<p>In other words, <mark>tagName</mark> is only supported by element nodes (as it 
originates from <mark>Element</mark> class), while <mark>nodeName</mark> can say 
something about other node types.</p>

<p>For instance, let’s compare <mark>tagName</mark> and <mark>nodeName</mark> for 
the <mark>document</mark> and a comment node:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
&lt;body&gt;&lt;!-- comment --&gt;

  &lt;script&gt;
    // for comment
    alert( document.body.firstChild.tagName ); // undefined (not an element)
    alert( document.body.firstChild.nodeName ); // #comment

    // for document
    alert( document.tagName ); // undefined (not an element)
    alert( document.nodeName ); // #document
  &lt;/script&gt;
&lt;/body&gt;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>If we only deal with elements, then we can use both <mark>tagName</mark> and 
<mark>nodeName</mark> – there’s no difference.</p>

<h4>The tag name is always uppercase except in XML mode</h4>
<p>The browser has two modes of processing documents: HTML and XML. Usually the HTML-mode 
is used for webpages. XML-mode is enabled when the browser receives an XML-document with the header: <mark>Content-Type: application/xml+xhtml</mark>.</p>

<p>In HTML mode <mark>tagName/nodeName</mark> is always uppercased: it’s <mark>BODY</mark> 
either for <mark>&lt;body&gt;</mark> or <mark>&lt;BoDy&gt;</mark>.</p>

<p>In XML mode the case is kept “as is”. Nowadays XML mode is rarely used.</p>

<h3><a href="">innerHTML: the contents</a></h3>
<p>The <span>innerHTML</span> property allows to get the HTML inside the element as a string.</p>

<p>We can also modify it. So it’s one of the most powerful ways to change the page.</p>

<p>The example shows the contents of <mark>document.body</mark> and then replaces it completely:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
&lt;body&gt;
  &lt;p&gt;A paragraph&lt;/p&gt;
  &lt;div&gt;A div&lt;/div&gt;

  &lt;script&gt;
    alert( document.body.innerHTML ); // read the current contents
    document.body.innerHTML = 'The new BODY!'; // replace it
  &lt;/script&gt;

&lt;/body&gt;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>We can try to insert invalid HTML, the browser will fix our errors:</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<pre>
&lt;body&gt;

  &lt;script&gt;
    document.body.innerHTML = '&lt;b&gt;test'; // forgot to close the tag
    alert( document.body.innerHTML ); // &lt;b&gt;test&lt;/b&gt; (fixed)
  &lt;/script&gt;

&lt;/body&gt;
</pre>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->

<h4>Scripts don’t execute</h4>

<p>If <mark>innerHTML</mark> inserts a <mark>&lt;script&gt;</mark> tag into the document 
– it becomes a part of HTML, but doesn’t execute.</p>

<h3>Beware: “innerHTML+=” does a full overwrite</h3>

<p>We can append HTML to an element by using <mark>elem.innerHTML+="more html"</mark>.</p>

<p>Like this:</p>

<pre>
chatDiv.innerHTML += "&lt;div&gt;Hello&lt;img src='smile.gif'/&gt; !&lt;/div&gt;";
chatDiv.innerHTML += "How goes?";
</pre>

<p>But we should be very careful about doing it, because what’s going on is not an 
addition, but a full overwrite.</p>

<p>Technically, these two lines do the same:</p>

<pre>
elem.innerHTML += "...";
// is a shorter way to write:
elem.innerHTML = elem.innerHTML + "..."
</pre>

<p>In other words, innerHTML+= does this:</p>

<ol type="1">
  <li>The old contents is removed.</li>
  <li>The new <mark>innerHTML</mark> is written instead (a concatenation of the old and 
    the new one).</li>
</ol>

<h4>As the content is “zeroed-out” and rewritten from the scratch, all images and other 
resources will be reloaded.</h4>

<p>In the <mark>chatDiv</mark> example above the line <mark>chatDiv.innerHTML+="How goes?"</mark> 
re-creates the HTML content and reloads <mark>smile.gif</mark> (hope it’s cached). If 
<mark>chatDiv</mark> has a lot of other text and images, then the reload becomes clearly 
visible.</p>

<p>There are other side-effects as well. For instance, if the existing text was selected 
with the mouse, then most browsers will remove the selection upon rewriting <mark>innerHTML</mark>. 
And if there was an <mark>&lt;input&gt;</mark> with a text entered by the visitor, then 
the text will be removed. And so on.</p>

<p>Luckily, there are other ways to add HTML besides <mark>innerHTML</mark>, and we’ll 
study them soon.</p>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3><a href="https://javascript.info/basic-dom-node-properties#outerhtml-full-html-of-the-element">
outerHTML: full HTML of the element</a></h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>The <mark>outerHTML</mark> property contains the full HTML of the element. That’s like 
<mark>innerHTML</mark> plus the element itself.</p>

<p>Here’s an example:</p>

<pre>
&lt;div id="elem"&gt;Hello &lt;b&gt;World&lt;/b&gt;&lt;/div&gt;

&lt;script&gt;
  alert(elem.outerHTML); // &lt;div id="elem">Hello &lt;b&gt;World&lt;/b&gt;&lt;/div&gt;
&lt;/script&gt;
</pre>

<h4>Beware: unlike innerHTML, writing to outerHTML does not change the element. Instead, 
it replaces it in the DOM.</h4>

<p>Yeah, sounds strange, and strange it is, that’s why we make a separate note about it 
here. Take a look.</p>

<p>Consider the example:</p>

<pre>
&lt;div&gt;Hello, world!&lt;/div&gt;

&lt;script&gt;
  let div = document.querySelector('div');

  // replace div.outerHTML with &lt;p&gt;...&lt;/p&gt;
  div.outerHTML = '&lt;p&gt;A new element&lt;/p&gt;'; // (&ast;)

  // Wow! 'div' is still the same!
  alert(div.outerHTML); // &lt;div&gt;Hello, world!&lt;/div&gt; (&ast;&ast;)
&lt;/script&gt;
</pre>

<p>Looks really odd, right?</p>

<p>In the line (*) we replaced div with <p>A new element</p>. In the outer document (the 
DOM) we can see the new content instead of the <div>. But, as we can see in line (**), 
the value of the old div variable hasn’t changed!</p>

<p>The outerHTML assignment does not modify the DOM element (the object referenced by, 
in this case, the variable ‘div’), but removes it from the DOM and inserts the new HTML 
in its place.</p>

<p>So what happened in div.outerHTML=... is:</p>

<p>div was removed from the document.</p>

Another piece of HTML <p>A new element</p> was inserted in its place.
div still has its old value. The new HTML wasn’t saved to any variable.
It’s so easy to make an error here: modify div.outerHTML and then continue to work 
with div as if it had the new content in it. But it doesn’t. Such thing is correct 
for innerHTML, but not for outerHTML.

We can write to elem.outerHTML, but should keep in mind that it doesn’t change the 
element we’re writing to (‘elem’). It puts the new HTML in its place instead. We 
can get references to the new elements by querying the DOM.

<h3>nodeValue/data: text node content</h3>
The innerHTML property is only valid for element nodes.

Other node types, such as text nodes, have their counterpart: nodeValue and data 
properties. These two are almost the same for practical use, there are only minor 
specification differences. So we’ll use data, because it’s shorter.

An example of reading the content of a text node and a comment:

<body>
  Hello
  <!-- Comment -->
  <script>
    let text = document.body.firstChild;
    alert(text.data); // Hello

    let comment = text.nextSibling;
    alert(comment.data); // Comment
  </script>
</body>
For text nodes we can imagine a reason to read or modify them, but why comments?

Sometimes developers embed information or template instructions into HTML in them, like 
this:

<!-- if isAdmin -->
  <div>Welcome, Admin!</div>
<!-- /if -->
…Then JavaScript can read it from data property and process embedded instructions.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>textContent: pure text</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The textContent provides access to the text inside the element: only text, minus all <tags>.

For instance:

<div id="news">
  <h1>Headline!</h1>
  <p>Martians attack people!</p>
</div>

<script>
  // Headline! Martians attack people!
  alert(news.textContent);
</script>
As we can see, only text is returned, as if all <tags> were cut out, but the text in them 
remained.

In practice, reading such text is rarely needed.

Writing to textContent is much more useful, because it allows to write text the “safe way”.

Let’s say we have an arbitrary string, for instance entered by a user, and want to show it.

With innerHTML we’ll have it inserted “as HTML”, with all HTML tags.
With textContent we’ll have it inserted “as text”, all symbols are treated literally.
Compare the two:

<div id="elem1"></div>
<div id="elem2"></div>

<script>
  let name = prompt("What's your name?", "<b>Winnie-the-Pooh!</b>");

  elem1.innerHTML = name;
  elem2.textContent = name;
</script>
The first <div> gets the name “as HTML”: all tags become tags, so we see the bold name.
The second <div> gets the name “as text”, so we literally see <b>Winnie-the-Pooh!</b>.
In most cases, we expect the text from a user, and want to treat it as text. We don’t 
want unexpected HTML in our site. An assignment to textContent does exactly that.

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>The “hidden” property</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
The “hidden” attribute and the DOM property specifies whether the element is visible or not.

We can use it in HTML or assign it using JavaScript, like this:

<pre>
<div>Both divs below are hidden</div>

<div hidden>With the attribute "hidden"</div>

<div id="elem">JavaScript assigned the property "hidden"</div>

<script>
  elem.hidden = true;
</script>
</pre>

<p>Technically, hidden works the same as style="display:none". But it’s shorter to write.</p>

<p>Here’s a blinking element:</p>

<pre>
<div id="elem">A blinking element</div>

<script>
  setInterval(() => elem.hidden = !elem.hidden, 1000);
</script>
</pre>

<h3>More properties</h3>
<p>DOM elements also have additional properties, in particular those that depend on the class:</p>

value – the value for <input>, <select> and <textarea> (HTMLInputElement, HTMLSelectElement…).
href – the “href” for <a href="..."> (HTMLAnchorElement).
id – the value of “id” attribute, for all elements (HTMLElement).
…and much more…
For instance:

<pre>
<input type="text" id="elem" value="value">

<script>
  alert(elem.type); // "text"
  alert(elem.id); // "elem"
  alert(elem.value); // value
</script>
</pre>

<p>Most standard HTML attributes have the corresponding DOM property, and we can access it like that.</p>

<p>If we want to know the full list of supported properties for a given class, we can find them in the specification. For instance, HTMLInputElement is documented at https://html.spec.whatwg.org/#htmlinputelement.</p>

<p>Or if we’d like to get them fast or are interested in a concrete browser specification – we can always output the element using console.dir(elem) and read the properties. Or explore “DOM properties” in the Elements tab of the browser developer tools.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Summary</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<p>Each DOM node belongs to a certain class. The classes form a hierarchy. The full set of properties and methods come as the result of inheritance.</p>

<p>Main DOM node properties are:</p>


nodeType
We can use it to see if a node is a text or an element node. It has a numeric value: 1 for elements,3 for text nodes, and a few others for other node types. Read-only.

nodeName/tagName
For elements, tag name (uppercased unless XML-mode). For non-element nodes nodeName describes what it is. Read-only.

innerHTML
The HTML content of the element. Can be modified.

outerHTML
The full HTML of the element. A write operation into elem.outerHTML does not touch elem itself. Instead it gets replaced with the new HTML in the outer context.

nodeValue/data
The content of a non-element node (text, comment). These two are almost the same, usually we use data. Can be modified.

textContent
The text inside the element: HTML minus all <tags>. Writing into it puts the text inside the element, with all special characters and tags treated exactly as text. Can safely insert user-generated text and protect from unwanted HTML insertions.

hidden
<p>When set to true, does the same as CSS display:none.</p>

<p>DOM nodes also have other properties depending on their class. For instance, &lt;input&gt; elements (HTMLInputElement) support value, type, while <a> elements (HTMLAnchorElement) support href etc. Most standard HTML attributes have a corresponding DOM property.</p>

<p>However, HTML attributes and DOM properties are not always the same, as we’ll see in the next chapter.</p>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h2>Tasks</h2>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Count descendants</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<small>importance: 5</small>
<p>There’s a tree structured as nested ul/li.</p>

<p>Write the code that for each &lt;li&gt; shows:</p>
<ol type="1">
  <li>What’s the text inside it (without the subtree)</li>
  <li>The number of nested &lt;li&gt; – all descendants, including the deeply nested ones.</li>
</ol>

<p>Demo in new window</p>

<p>Open a sandbox for the task.</p>

<h4>solution</h4>

<h3>What's in the nodeType?</h3>
<small>importance: 5</small>
<p>What does the script show?</p>
<pre>
&lt;html&gt;

&lt;body&gt;
  &lt;script&gt;
    alert(document.body.lastChild.nodeType);
  &lt;/script&gt;
&lt;/body&gt;

&lt;/html&gt;
</pre>

<h4>solution</h4>

<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<h3>Tag in comment</h3>
<!--~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-->
<small>importance: 3</small>

<p>What does this code show?</p>

<pre>
&lt;script&gt;
  let body = document.body;

  body.innerHTML = "&lt;!--" + body.tagName + "--&gt;";

  alert( body.firstChild.data ); // what's here?
&lt;/script&gt;
</pre>

<h4>solution</h4>
<h3>Where's the "document" in the hierarchy?</h3>
importance: 4

<h4>Which class does the document belong to?</h4>

<p>What’s its place in the DOM hierarchy?</p>

<p>Does it inherit from Node or Element, or maybe HTMLElement?</p>

<h4>solution</h4>

<p>We can see which class it belongs by outputting it, like:</p>

<pre>alert(document); // [object HTMLDocument]</pre>
<p>Or:</p>

<pre>alert(document.constructor.name); // HTMLDocument</pre>
<p>So, document is an instance of HTMLDocument class.</p>

<p>What’s its place in the hierarchy?</p>

<p>Yeah, we could browse the specification, but it would be faster to figure out manually.</p>

<p>Let’s traverse the prototype chain via __proto__.</p>

<p>As we know, methods of a class are in the prototype of the constructor. For instance, 
HTMLDocument.prototype has methods for documents.</p>

<p>Also, there’s a reference to the constructor function inside the prototype:</p>

<pre>alert(HTMLDocument.prototype.constructor === HTMLDocument); // true</pre>

<p>To get a name of the class as a string, we can use constructor.name. Let’s do it for the whole document prototype chain, till class Node:</p>

<pre>
alert(HTMLDocument.prototype.constructor.name); // HTMLDocument
alert(HTMLDocument.prototype.__proto__.constructor.name); // Document
alert(HTMLDocument.prototype.__proto__.__proto__.constructor.name); // Node
</pre>

<p>That’s the hierarchy.</p>

<p>We also could examine the object using <mark>console.dir(document)</mark> and see 
these names by opening <mark>__proto__</mark>. The console takes them from <mark>constructor</mark> internally.</p>
