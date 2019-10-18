# HTML Cheatsheet

### Every HTML file must have four elements. These are needed for page structure:
```html
<!DOCTYPE html> <!-- Declaration: tells browser type of code -->
<html> <!-- Tells browser everything inbetween the two tags is HTML -->
	<head> <!-- Meta info, wont appear on actaul page -->
	</head>
	<body> <!-- Place for markup that's going to apperar on the site -->
	</body>
</html>
```
### Everything that can go in the `<head>` tag :
```html
<head>
	<title>HTML CheatSheet<title> <!-- (Required) gives title to page and appears in tab -->
	<meta name="value" pairs> <!-- Always in <head>, provides information about the data -->
	<meta name="description" content="Descriptive HTML CheatSheet"> <!-- The content attribute MUST be defined if the name is defined -->
	<style type="text/css">
		h1 {color:red;}
    </style> <!-- Defines style information for an HTML document -->
    <link rel="icon" href="favicon.io"> <!-- Defines a link between a document and an external resource. -->
    <script > 
    </script> <!-- Used to embed or refer to JavaScript code -- >
</head>
```
\*Best Practice* :
* Better to use an external stylesheet and using the `<link>` than `<style>`.
* `<script>` should be in the `<head>` and use the async or defer attributes. This allows scripts to be downloaded ASAP without blocking your browser.
* For users that have disabled scripts in their browser, or have a browser that doesn't support client-side scripting use `<noscript>`.

### In the `<body>` tag a whole array of data can be passed through a variety of tags/elements. The following tags/elements are used to section and outline the page:
``` html 
<body>
	<header>
    </header> <!-- Typically contains the logo, title, and (navigation.)-->
    
    <nav>
    </nav> <!-- The <nav> element indicates a navigation block and mainly used for major navigational menus.-->
    
    <main>
        <section>
        </section> <!-- Used for thematic grouping of content, a section of the page.-->
        
        <article>
        </article> <!-- Used to indicates (independent) self-contained content.-->
        
        <aside>
        </aside> <!-- Used for related content that has a different placement than the main content. It is often used for call-outs, blockquotes, sidebars and definitions.-->

        <span>
        </span> <!-- used to group inline-elements in a document. Usually used for CSS hooks(non-semantic wrapper)-->

        <div>
        </div> <!-- Defines a division or a section in an document usually for CSS hooks (non-semantic wrapper)-->
    </main> <!-- Specifies the main content of a document.-->

	<footer>
	</footer> <!-- Typically contains the copyright, legal notices and sometimes some links-->
</body>
```
\*Best Practice* :
* Majority of these elements can nest within each other except for `<nav>` which cannot have any of these nesting in them.
* `<main>` is strictly informative it shouldnt include content that is repeated across a set of documentsmor document sections e.g. nav and search forms. 

### Within these sectioning and outlining elements a whole selection of semantic tags/element can be used: 
```html
   <!-- Headings -->
    <h1>Heading One</h1>
    <h2>Heading Two</h2>
    <h3>Heading Three</h3>
    <h4>Heading Four</h4>
    <h5>Heading Five</h5>
    <h6>Heading Six</h6>

    <hr> <!-- Outputs a horizontal line-->

   <!-- Paragraph -->
    <p> <!-- Defines a paragraph-->
        <u>These tags underline content</u>, <i>these tags make content italics</i>, sed do eiusmod
        tempor <strong>these tags makes content bold </strong> et dolore magna aliqua. <b>these tags make content bold too</b>,
        quis nostrud <em>these tags makes content italics too </em> laboris nisi ut aliquip ex ea commodo
        consequat. Duis <a href="http://google.com" target="_blank">this tag makes content become a link must include attributes and values</a> aute irure. <b>The following tags make format content so it's defined in human readable terms</b> Christmas is the <time>25<sup><!--Superscript-->th</sup> December</time>
    </p>
  
   <!--HTML interactivity-->
    <details>
       <summary> Click me the heading for hidden content</summary>
       <p>Expandable content</p>
    </details> <!-- Specifies additional details that the user can view or hide on demand-->
    
   <!-- Quotations -->
    <blockquote>
       <p><i><a href=""><cite>These tags define the title of a work</cite></a> says:</i></p>
 	  	<q>These tags define short quotation</q>
    </blockquote> <!-- Specifies a section that is quoted from another source.-->

   <!--Abbreviation-->
    <p>The <abbr title="World Wide Web">WWW</abbr> <!-- Defines an abbreviation or an acronym--> is awesome</p>

   <!-- Lists -->
    <ul> <!-- Creates an unordered list-->
        <li>List Item 1</li> <!-- Used to creat ind. listitems-->
        <li>List Item 2</li>
    </ul>

    <ol><!-- Creates an ordered list-->
        <li>List Item 1</li>
        <li>List Item 2</li>
    </ol>
   
   <br> <!-- Inserts a single line break.-->

   <!-- Table -->
    <table> <!-- Creates a table-->
        <thead> <!-- Used to group header content in an table.-->
            <tr> <!-- Defines a row in an HTML table.-->
                <th>Name</th> <!-- Defines a header cell in an HTML table.-->
                <th>Email</th>
                <th>Age</th>
            </tr>
        </thead>
        <tbody> <!-- Used to group the body content in an table.-->
            <tr>
                <td>John Doe</td> <!-- defines a standard cell in an HTML table-->
                <td>jdoe@something.com</td>
                <td>45</td>
            </tr>
        </tbody>
    </table>

    <!-- Button -->
    <button>Click Me</button> <!-- Defines a clickable button.-->
```

### Use of these tags/elements enables inclusion of multimedia into a web page:
```html
   <!-- Image -->
    
    <figure> <!-- Specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.-->
        <picture> <!-- Used to give more flexibility in specifying image resources.-->
            <source srcset="" media="(min-width:650px)"> <!-- Used to specify multiple media resources for media elements-->
            <img src="images/sample.jpg" alt="My Sample Image" width="auto"> <!-- Defines an image in an HTML page.-->
        </picture>
      
 	    <figcaption>defines a caption for a <figure> element.</figcaption>
 	</figure>
    
   <!--Video-->

    <video controls> <!-- Specifies video, such as a movie clip or other video streams.-->
        <source src="rabbit320.mp4" type="video/mp4">
        <source src="rabbit320.webm" type="video/webm">
        <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
    </video>

   <!--Audio-->
   
    <audio controls> <!-- Defines sound, such as music or other audio streams.-->
        <source src="viper.mp3" type="audio/mp3">
        <source src="viper.ogg" type="audio/ogg">
        <p>Your browser doesn't support HTML5 audio. Here is a <a href="viper.mp3">link to the audio</a> instead.</p>
    </audio>
```
\*Best Practice* :
* `<img>` is usually suffice on it own with need of the other elements any styling can be done with CSS. 

### Use of these tags/eleemnts allows for greater user interaction:
```html 
   <!-- Forms -->
    <form action="process.php" method="POST"> <!-- Used to create an HTML form for user input. -->
       <fieldset> 
        <legend>Title</legend> <!-- defines a caption for the <fieldset> element.-->
        <input type="radio" name="radio" id="radio">
        <label for="radio">Mr.</label>
       </fieldset> <!--used to group related elements in a form.-->
        <label> First Name</label><!-- Defines a label for other form elements-->
        <input type="text" name="firstName" placeholder="Enter first name"> <!-- Specifies an input field where the user can enter data.-->
        <label>Message</label>
        <textarea name="message"></textarea><!-- Defines a multi-line text input control.-->
        <label>Gender</label>
        <select name="gender"> <!-- Used to create a drop-down list.-->
            <option value="male">Male</option> <!-- Defines the available options in the list.-->
            <option value="female">Female</option>
            <option value="other">Other</option>
        </select>
        <label>Age:</label>
        <input type="number" name="age" value="30">
        <label>Birthday:</label>
        <input type="date" name="birthday">
        <input type="submit" name="submit" value="Submit">
    </form>
 ```
\*Best Practice* :
* `<input>` most important part is the type attribute, pick th eright one for the job.


