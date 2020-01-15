# CSS Cheatsheet

### There are three methods of adding CSS to HTML:
1. Inline CSS - `<h1 style='color:red'>hello</h1>`
2. Internal CSS - 
```html
<head>
    <style type="text/css">
        h1{
            color:blue;
        } 
    </style>
```
3. External CSS -
```html 
<head>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>
```
\*Best Practice* :
* Use External CSS as it's more beneficial e.g reusability, SoC etc.

### Selectors allow you to add styling to a particular place and to do this there several ways which also vary in hiarchy:
* Element - There are two types of these selectors:
    - `element {}` these are normal html elements e.g. `<a>`.
    - `element::pseudo-element {}` these are [keywords][1] added to an element selector that styles a specific part of the selected element(s).
* Class/Attr - there are three types of these selectors:
    - `.class {}` these are the class attribute in html opening tag `<p class="value">`
    - `element[attribute] {}` these match elements based on the [presence or value][2] of a given attribute.
    - `element:pseudo-class {}` these are [keywords][3] added to an element selector that specifies a special state of the selected element(s).
* id - `#id {}` these are the id attribute in an html opening tag `<p id="value">`
* complex selectors - other ways of selecting include:
    - child and sibling -
    ```css
    /*descendant*/
    li li {} /*Selects all <li> elements inside <li> elements*/
    /*direct child*/
    div > p {} /*Selects all <p> elements where the parent is a <div> element*/
    /*sibling*/
    p ~ ul {} /*Selects every <ul> element that are preceded by a <p> element*/
    /*adjacent sibling*/
    a + img {} /*Selects all <p> elements that are placed immediately after <div> elements*/
    ```
    - combining - `th, td, p.red, div#firstred {}` you can also use commas to combine multiple selectors with same styling. 

\*Best Practice* :
* When using selectors two things are important; Order - latest rule applies and Specificity heirachy - Inline styles>Ids>Class/Attr>Elements.

### Once the correct selector is chosen we open the declaration `{}` inside her goes the `{property: value;}` (pairings). These properties can be categorized for easier understanding to what they do (lists dont cover all properties): 
* Content-
    - [Font/text styling][4] - 
    ```css
   p{
     color:#555555;

	 font-family: Arial, Helvetica, sans-serif;
	 font-size:16px;
     font-weight:normal;
    
     text-decoration: underline;
     text-transform: uppercase;
     text-shadow: 1px 1px 1px black;
    }
    ```
    - [List][5] and [Links][6] -
    ```css
    ol{
        list-style-type: upper-roman;
        list-style-position: inside;
        list-style-image: url(star.svg);
    }

    a{
        text-decoration: none;
        color:#000;
    }

    a:hover{
        color:red;
    }

    a:active{
        color:green;
    }
    ```
    - [Multimedia and forms][7] -
    ```css
    img {
        object-fit: cover;
        object-fit: contain;

        width: 100%;
        height: 100%;

        background-image: url('../images/bgimage.jpg');
        background-repeat: no-repeat;
        background-position:100px 200px;
        background-position:center top;
    }

    textarea {
        overflow: auto;
    }
    ```
* [Layout][13]-
    - [Box model][8]
    ```css
    label{
        display: block;
        display: inline;
        display: inline-block;

        width: 350px;
        height: 150px;

        min-width: 450px;
        max-width: 650px;

        overflow: hidden;

        padding-top: 20px;
        padding-bottom: 20px;
        padding-right: 20px;
        padding-left: 20px;

        /* Short-hand */
        padding: 20px;

        border-right-width: 5px red solid;
        border-left-width: 5px red solid;
        border-top-width: 5px red solid;
        border-bottom-width: 5px red solid;

        /* Short-Hand*/
        border-width: 5px red solid;

        margin: 20px 0;

        box-sizing: border-box;
    }    
    ```
    - [Floating][10] and [Positioning][9].
    ```css
    .container{
        display: flow-root;
        overflow: auto;

        float: none;
        float: left;
        float: right;
        float: inline-start;
        float: inline-end;

        position: static;
        position: relative;
    }

    .container h1{
        position: absolute;
        top: 100px;
        left: 200px;
    }

    .container h2{
        position: absolute;
        bottom: 40px;
        right: 100px;
    }

    dt{
        position: sticky;
        top: 0;
        left: 0;
    }

    .nav-bar{
        position: fixed;
        top: 400px;
    }
    ```
    - [Flexbox][11]
    ```css
    .container{
        display: flex; /* or inline-flex */

        flex-direction: row; /* row-reverse, column, column-reverse */
        flex-wrap: nowrap; /* wrap, rap-reverse */

        flex-flow: row nowrap; /* flex-direction and flex-wrap */

        justify-content: flex-start; /* flex-end, center, space-between, space-around,  space-evenly, start, end, left, right */

        align-items: stretch; /* flex-start, flex-end, center, baseline */

        align-content: flex-start; /* flex-end, center, space-between, space-around, space-evenly, stretch, baseline */
    }

    .items{
        order: 0;

        flex-grow: 0;
        flex-shrink: 0;
        flex-basis: 10px; /* auto, content*/

        flex: 0 1 auto; /* flex-grow, flex-shrink and flex-basis */

        align-self: auto; /* flex-start, flex-end, center, baseline, stretch */
    }
    ```
    - [Grid][12]
    ```css
    .container {
        display: grid; /* inline-grid */

        /* Tracks (explicit) */
        grid-template-columns: 1px; /* %, fr, auto, [name] size/fr, repeat(any of prev) */
        grid-template-rows: 1px; /* %, fr, auto, [name] size/fr, repeat(any of prev) */

        grid-template-areas: "<string>";  /* ., ..., none */

        /*Shorthand*/
        grid-template: <row val> "<string>" / <column val>; /* none, <grid-template-rows> /<grid-template-columns> */
        
        /* Tracks (implicit) */
        grid-auto-columns: 1px; /* %, fr, auto, minmax(any of prev, amy of prev), min-content */
        grid-auto-rows: 1px; /* %, fr, auto, minmax(any of prev, amy of prev), min-content */

        grid-auto-flow: row; /* column, row dense, column dense */

        /*Shorthand for all*/
        grid: explicit/implicit (either/or); /* */
        grid: 100px 300px / 3fr 1fr; /*[ auto-flow && dense? ] <'grid-auto-columns'>, [ auto-flow && dense? ] <'grid-auto-rows'> / <'grid-template-columns'> */

        row-gap: 15px; /*<line-size>;*/column-gap: 10px; /*<line-size>*/
        
        /*Shorthand*/
        gap: 15px 10px; /*<row-gap> <column-gap>*/

        justify-items: stretch; /* start, end, center, stretch; */
        align-items: stretch; /* start, end, center; */
        
        /*Shorthand */
        place-items: auto; /* <align-items> / <justify-items> */

        justify-content: stretch; /* start, end, center, space-around, space-between, space-evenly*/
        align-content: stretch; /* start, end, center, space-around, space-between, space-evenly */

        /*Shorthand */
        place-content: auto; /* <align-items> / <justify-items> */
    }

    .items{
        grid-column-start: 2; /* <name>, span <number>, span <name>, auto;*/
        grid-column-end: span 4; /* <name>, <number>, span <name>, auto; */
        grid-row-start: three; /*<number>, span <number>, span <name>, auto; */
        grid-row-end: span row4-end; /*<number>, <name>, span <number>, auto;*/

        /*Shorthand*/
        grid-column: third-line / 4; /* <start-line> / span <value>; */
        grid-row:  3 / span 2; /*<start-line> / <end-line>; */

        /*Shorter Shorthand */
        grid-area: header; /*<row-start> / <column-start> / <row-end> / <column-end>;*/
        grid-area: 1 / col4-start / last-line / 6; /* <name> */

        justify-self: stretch; /* start, end, center, stretch; */
        align-self: stretch; /* start, end, center; */

        /*Shorthand */
        place-self: auto; /* <align-self> / <justify-self> */
    }
    ```
[1]: https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements
[2]: https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors
[3]: https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes
[4]: https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals
[5]: https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_lists
[6]: https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_links
[7]: https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Images_media_form_elements
[8]: https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model
[9]: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning
[10]: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats
[11]: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox
[12]: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids
[13]: https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction