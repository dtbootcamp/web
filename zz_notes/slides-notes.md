BOOTCAMP WEB CURRICULUM SLIDE NOTES
======
#### These are notes on the lecture slides for the Web portion of DT Bootcamp 2014.
## Overall Curiculum Notes
- when should we introduce the in-browser dev-tools? Perhaps....
  - one of the first days to let people mess around with "breaking" a website. This sounds like fun.
  - Re-introduce it later to show practical applications, for example how you can adjust your CSS styles on the fly.
  - Show the javascript console during the intro to JS days.
- we should talk about or at least mention responsive design.


## Day 01:

### overall: 
- make more visual? Add photos?

### individual slides:

- 26: fix grammar: “Didn’t found 404 error HTTP respond” > “Didn’t find / 404 HTTP response”
- 29: example of the bold tag `<b>` ~~isn’t good because we don’t use it anymore.~~ (semantic meaning has changed in html5)
- 34: server side programming: add “databases” as an example. Not many people will know what SQL is.
- 35: server side languages: add UNIX, Python, Ruby
- 36: diagram is a little confusing, maybe re-work it?
- 37: not all webpages use databases (for example one page websites)

## Day 02:
### overall: 
- looks unfinished? Could explain more about DOM tags? Day Two seems a little weak?
- talk about how important ""semantics" are in HTML, for example why use `<section>` or `<header>` over `<div>`?
- mention differences in html declaration, meta, script and link tags from html4 to html5 (basically they've been simplified) 


### individual slides:

- 02: to me, at the simplest level a web page is series of containers / boxes that contain text, images, color, etc. arranged in a certain order.
- 05: “Often a page contains content that moves or changes while the rest of the page remains the same.” sounds strange, clarify?
- 07: I would rephrase this to say “many technologies (such as …) may be used to create web pages.
- 13: “be sure that every device will display the web page in the same way.” is deceiving, devices WILL certainly render pages differently!
- 17: “surround” should be “surrounds”. I would use the word “contains” over “surrounds” as this is more clear of how html actually works. (a series of containers or boxes)
- 18: explain how we make html human readable by “nesting” code.
- this lesson seems a little short, should we dive into types of other html tags more in this lesson?



## Day 03: More HTML and Intro to CSS
### overall:
~~!important: I don’t have power point on my machine so the fonts get messed up. Save as PDF?~~ 

- mention new html5 elements for improved semantics from html4: 

  - Section
  - Header
  - Footer
  - Aside
  - Nav
  - Article
  - Main
  - Figure/figcaption
  - Time  
  
- for example, the difference from html4 to html5 using the new `<aside>` element would look like:
  
  ```
  <!— html4 —>
  <div class="sidebar">
    <!-- content here -->
  </div>
  
  <!— html5 —>
  <aside>
    <!-- content here -->
  </aside>
  ```
  
  - another example:
  
  ```
  <section>
    <header>
      <h1>A heading of a section</h1>
      <p>Some content in the header.</p>
    </header>
    <p>Some stuff within the section.</p>
    <footer>
      <p>By "Blogger Name"</p>
    </footer>
  </section>
  ``` 

### individual slides:
- 12 & 13: add some words to the un-ordered list tags so they aren’t empty (not sure if this is because I’m viewing the file in keynote)
- 14: mention while it is possible to style html with these tags it is more preferable to do it with CSS
- 26: also mention the `!important` method and inline style attribute `<div style="width:20px;height:20px;background-color:#ffcc00;"></div>` 
  - explain what the preferred method of doing this is and why. Answer [here](http://stackoverflow.com/  questions/12013532/inline-style-tags-vs-inline-css-properties) is good.   
- 26: this might also be a good time to explain the concept of accessing an external file via a path, eg:
  -  `<link rel="style.css">`  
  - `<link rel="css/style.css">` 	 
  - `<link rel="../css/style.css">`  
- 27: you don’t explain what id’s and classes are before mentioning this.
- for the homework assignment they can also create a boilerplate template that can be loaded in Sublime with a shortcut command (super helpful!)

## Day 04: CSS
### overall:
- describe what CSS3 is and what the new properties are that come with it, such as:

  - Border Radius
  - Box Shadow
  - Box Sizing
  - Multiple Backgrounds
  - Color
  - Opacity
  - Gradients 

- mention 'key words' in CSS and how some of them have equivalent mathematical terms.
- talk about the @font-face attribute, other ways of using external fonts, the concept of fallback fonts and how to use unicode characters.
- talk about text shadows
- mention CSS compilers like Sass and Less (just that they exist and why they are useful --we obvious aren't going to teach them).

### individual slides:
- 11: say why this (over specificity) is a bad practice and to be avoided at all costs! 
  - also this is somewhat confusing because you can use the wildcard * to select all elements, for example:

  css:

  ```
  body * { font-weight: normal; }
  #stockTicker { font: 12px Verdana; }
  .corpName { font-weight: bold; }
  .stockUp { color: red; }
  ```

  html:

  `<div id="section">`
     `NYS: <span class="corpName"><span class="stockUp">GE</span></span>`
  `</div>`



“In this example the body * selector applies the rule to all elements inside body, at any hierarchy level, including the .stockUp class. So font-weight: bold; applied to the .corpName class is overridden by font-weight: normal; applied to all elements in the body.

The use of the * selector should be minimized as it is a slow selector, especially when not used as the first element of a selector. Its use should be avoided as much as possible.” 

(from: https://developer.mozilla.org/en-US/docs/Web/CSS/Common_CSS_Questions)

- 12: also mention that other types of psuedo classes exist, such as :before and :after. A full list [here](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

- 14: a good way to think about specificity is as a four digit comma separated list: 
  0,0,0,0 that maps to —> inline styles, # of id selectors, # of class selectors, # of element selectors
  - note the `!important` value will override all of these
  - if digits in two or more places are the same number then CSS will default to the last one in the list
  - but if there is a digit > 0 before the following digit it will override following methods
    (ie: 0,1,2,2 —— if you have 1 id but 2 classes and 2 element selectors the id will override all the class and element selectors)

- 17: most modern web browsers support the use of hsl() for color. Also mention the alpha property for rgba and hsla

- 24: related, I found this interesting on [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size):
“A popular technique to use throughout the document is to set the the font-size of the body to 62.5% (that is 62.5% of the default of 16px), which equates to 10px, or 0.625em. Now you can set the font-size for any elements using em units, with an easy-to-remember conversion, by dividing the px value by 10. This way 6px = 0.6em, 8px = 0.8em, 12px = 1.2em, 14px = 1.4em, 16px = 1.6em. For example: ”

  ```
  body {
    font-size: 62.5%; /* font-size 1em = 10px */
  }
  p {
    font-size: 1.6em; /* 1.6em = 16px */
  }
  ```

- “The em is a very useful unit in CSS, since it can adapt automatically to the font that the reader chooses to use.”  

- 27: Might be a good time to mention the concept of DRY (Don’t Repeat Yourself). You cover some of these but together they apply to DRY. 

  ie:
  - using inheritance 
  - using classes over id’s
  - using commas to separate multiple selectors and set properties for them at once
  - selector abstraction, ie: if you’re setting multiple classes to the same properties combine them to one class, then if you need to differentiate add a sub-class
  - remembering order in CSS matters!

- also:
  - there are other shorthand CSS properties worth mentioning:

    ```
    font: 16px/18px bold italic sans-serif;
    /* size/line-height weight style family */

    background: #000 url(image.jpg) no-repeat center top;
    /* color image repeat x-pos y-pos */

    list-style: disc inside none;
    /* style position image */

    margin or padding: 0 10px 0 10px / 0 10px 0 / 0 10px;
    /* top right bottom left / top right&left bottom / top&bottom right&left */

    border: 3px solid #ccc;
    /* width style color */
    ```

## Day 05: Web Design Process and CSS Box Model

### overall:  
- Great visuals but adding some text to compliment would be really helpful. This could be a separate document in the form of notes that go along with each slide.
- Think this should be split into 2 separate slide shows. One titled “The Web Design Process” and another titled “The Box Model and Positioning with CSS”
- talk about using grids consisting of gutters and columns to organize content on web pages.
- mention accessability in web design as outlined in the [Web Content Accessibility Guidelines](http://www.w3.org/WAI/intro/wcag)
- probably not worth going into great detail about but worth mentioning the [document outline](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Sections_and_Outlines_of_an_HTML5_document) for organizing content in web pages.
- talk about the issue of "progressive enhancement" (designing so that webpages have fallbacks for older browsers.)
- talk about responsive design & the `@media` query. [Here is a good article](http://bradfrostweb.com/blog/web/responsive-web-design-missing-the-point/)
  - [MDN page on media queries in CSS](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Media_queries) 
  - explain the formula: `target / context = result` for converting pixels to em's or percentages.
    - the default browser text size is 16px but this is a hard number to work with mathematically. So set the body `font-size` property to 10px.
    - eg: `30px / 10px = 3em`
    - if your website's total width is 940px, set its elements relative value in percentages
    - eg: a sidebar is 325px wide. so: `325px/940px = 0.34574468085106 = 34.574468%`
    - [here](http://responsv.com/flexible-math/) is a good tool for doing this quickly and generating CSS output automatically :)
- mention the [collapsing margins problem](http://www.w3.org/TR/CSS2/box.html#collapsing-margins) in CSS.


### individual slides:
- 10: related: should we explain or at least mention templates that exist already such as bootstrap?
- 12: Maybe use solid colors to show each area? Sort of hard to look at / comprehend if you’ve never heard of the box-model before, especially because borders on elements in websites are usually very thin.
- 13: this diagram is confusing to look at, looks more like it should be used to explain z-index? Not clear from this that margin is not affected by background-color while padding is.
- 15: more elements than just margins use these units, can be applied to other elements with CSS as well
- 19 & 22: think the difference between border and padding would be more easy to see if you also visualized neighboring elements next to the box in the examples. Right now it’s hard to tell the difference between the two visually.
- 31: maybe add the word “flow”? ie: “…and occurs where it normally would in the document flow.”
- 32: mention that the origin in all web layout 0,0 is the top-left corner.
- 35: ended slide show without talking about position: fixed; Explain when / why you would want to use this.


## Day 06: Floats
### overall:
- state types of float: `float: left / right / none`
- other important properties of floats to mention:
  - floated elements stack up to parent edge, then move down to next available edge
  - if floated elements are a different height then the next shorter element will float against a taller element when moving down.
  - if not enough horizontal room the element that appears first in the DOM will be placed at the top
  - if both are floated right the first element in the html will be to the farthest right

### individual slides:
- 12: clearing floats, add:
  - if the other items inside container are in danger of not extending beyond the floated item the parent container isn’t going to stretch to match the height of any floated items!
  - necessary to clear the float of any floated items if it extends beyond the content of non-floated items.
  - if all elements inside container are floating it will be necessary to clear the container as well.

#### 3 methods for clearing floats
1. Clear with a subsequent element
   - next element has `clear: both;`

2. Manual clearing
   - next sibling element is empty and has `clear: both;`
   - works for extending background or border of parent container to stretch to height of parent elements

3. Clearfix
   - recommended method
   - add group class to parent container to self clear any elements inside of it.
   - allows for not needing a subsequent or empty element to extend height of container.
   - __css code:__

      ```
      /* clearfix */
        
      .group:before,
      .group:after {
        content: "";
        display: table;
      }
      .group:after {
        clear: both;
      }
      .group {
        zoom: 1;
      }
      ```

__Additional Reading:__

- stack overflow: [What is clearfix?](http://stackoverflow.com/questions/8554043/what-is-clearfix) 
- css tricks: [Force Element To Self-Clear its Children](http://css-tricks.com/snippets/css/clear-fix/)

## Day 07:	Floats Continued and Transitions

### overall:
- no slides yet

### individual slides:

- no slides yet

## Day 08: Media on Web
### overall:
- mention iframe?
- mention SVG
  - how you can take code from an SVG file you save in illustrator and embed it on a webpage and/or
  - copy the SVG source code from a webpage, save it to a file and open it in Illustrator.
- mention methods of image cropping with and without CSS
- mention responsive image / media sizing using percentages
  - eg:
    1. Save image larger than needed
    2. add `max-width: 100%` property to `img` tag at top of your CSS: img { max-width: 100%; } 
    3. then in the specific image tag set the `max-width` property again to the size you want in %:

   ```
   .item img {
     max-width: 26.785%
   }
   ```
   
  - You can also do this with other media types, eg: embed, video, object, etc.
- mention image sprites (ie having an image icon in multiple states saved in the same file, then adjusting using CSS to show the correct icon / state for things like `:hover`)
- mention background images using CSS for layout vs. inline images using `<img>` tag for content
- when using a background image and still want descriptive text for accessibility
  - using the text-indent property can get rid of text from viewport: 
    
    ```
    .logo {
    background: url(logo.png);
    display: block;
    height: 100px;
    width: 200px;
    text-indent: -9999px;
    }
    ```

### individual slides:
- 06 & 09: mention html5 audio and video elements explained [here](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML5_audio_and_video).


## Day 11: Intro to JS
### overall:

__Stuff to add to the JS curriculum:__

- examples of how JS is used on the web (maps, forms, drop down menus, etc), what is JS even for?
- where does CSS end and JS begin?
- images! GIFs!
- mention Node JS
- mention libraries
- mention API's

### Suggested order of topics to introduce:


#### Why is JS important to learn?
  - it’s what makes the web dynamic (though now CSS is contributing as well as we saw with the transition property)
  - there are tons of JS libraries out there for making your life easier when doing web design and development.
  - it's being used increasingly for server side programming with Node JS.
  - some examples of cool things that use JS
    - http://nyctaxi.herokuapp.com/
    - https://www.google.com/maps/preview
    - http://www.patatap.com/

#### Intro to JS slides
- *have students follow along by typing examples in the console.*

- explain to students that the console is not scary! You can’t break anything :)

### Then, while going through the slides...

#### start with numeric values
- doing math in console, eg: write an expression that evaluates to 49.
- doing boolean tests, eg: what does 4 !== 5 evaluate to?

#### Move onto Strings
- make sure to not do things like: `“some string here’` -- (note the " and ' )
- escaping characters, newlines, tab stops. eg: `"Quoth the raven:\n\t\"Nevermore!\""`
- demo concatenation: `'Hello ' + 'World!'`
- boolean tests with strings: `'MFA DT' === 'MFA TD'` -- returns `false`
- using the built-in `.length` method: `‘How many characters are in this sentence?’.length;`
  
#### Variables
- explain syntax: variable keyword `var`, variableName, assignment operator `=`, value to be stored, semicolon `;`
  - eg: `var numberStudents = 15;`

- rules / good practices for naming variables in JS:
    - no spaces in names
    - no digits in front of name but digits at end of variable name are okay.
      - eg: `2students` will break the code but `students2` will not.
    - camelCase is preferred, underscores are okay.
      - hereIsAReallyLongVariableName;
      - here_is_a_really_long_variable_name;
    - avoid dollar signs (for now) and reserved words & symbols.

- changing variable contents:
    - no need to use `var` if already assigned and updating value.
    - using current value to calculate new values: 
      - `numStudents - 2` or `numStudents -= 2`
    - variables as substitutes for data they point to: 
      - `“We have “ + numStudents + “ in our classroom.”` or `halfStudents = numStudents / 2`
    - can also store strings: `welcomeStudents = “hello class! it’s a pleasure to have you :)”`
    - length property: `welcomeStudents.length;`
    - indexing strings (starts at 0) and accessing using .charAt() method: 
      - `welcomeStudents.charAt(1);` -- returns “e”

- making versitile messages with variables
  - `var totalStudents = 91; var brooklynStudents = 26; “There are “ + brooklynStudents + “ out of “ + totalStudents + “ in our program.”`

#### From the console to a file
- linking an external js file using `<script src=“somefile.js”></script>` in either the `<head>` or `<body>` elements.
- good practices to keep your code clean and human readable.
  - indenting 2 spaces
  - camelCase
  - using comments
  - using semantics for naming things like variables and functions 
- don’t forget semi-colons!
- `console.log()`’ing things: `console.log(brooklynStudents == totalStudents);`




### Notes on individual slides:
- 9: go over language differences between Java (Processing) and JS in more detail? Maybe make examples more relevant to Processing?

## Day 12: JS Continued

### overall:
- explain how to target html elements with `document.querySelector(selectors);`
- explain debugging with dev-tools and the console.

### individual slides:
- no slides for this class as students will code along with the dot-js	 example [here](https://github.com/dtbootcamp/web/blob/master/day_11_12/dot-generator-no-app.html)








