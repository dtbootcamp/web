BOOTCAMP WEB CURRICULUM SLIDE NOTES
======
## Day 01:

### overall: 
- make more visual? Add photos?

### individual slides:

- 26: fix grammar: “Didn’t found 404 error HTTP respond” > “Didn’t find / 404 HTTP response”
- 29: example of the bold tag `<b>` isn’t good because we don’t use it anymore. 
- 34: server side programming: add “databases” as an example. Not many people will know what SQL is.
- 35: server side languages: add UNIX, Python, Ruby
- 36: diagram is a little confusing, maybe re-work it?
- 37: not all webpages use databases

## Day 02:
### overall: 
- looks unfinished? Could explain more about DOM tags? Day Two seems a little weak?

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
!important: I don’t have power point on my machine so the fonts get messed up. Save as PDF?

### individual slides:
- 12 & 13: add some words to the un-ordered list tags so they aren’t empty (not sure if this is because I’m viewing the file in keynote)
- 14: mention while it is possible to style html with these tags it is more preferable to do it with CSS
- 26: also mention the `!important` method and inline style attribute `<div style="width:20px;height:20px;background-color:#ffcc00;"></div>`
  - explain what the preferred method of doing this is and why. Answer [here](http://stackoverflow.com/questions/12013532/inline-style-tags-vs-inline-css-properties) is good.   
- 27: you don’t explain what id’s and classes are before mentioning this.
- for the homework assignment they can also create a boilerplate template that can be loaded in Sublime with a shortcut command (super helpful!)

## Day 04: CSS
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

- 24: related, I found this interesting on [mdn] (https://developer.mozilla.org/en-US/docs/Web/CSS/font-size):
“A popular technique to use throughout the document is to set the the font-size of the body to 62.5% (that is 62.5% of the default of 16px), which equates to 10px, or 0.625em. Now you can set the font-size for any elements using em units, with an easy-to-remember conversion, by dividing the px value by 10. This way 6px = 0.6em, 8px = 0.8em, 12px = 1.2em, 14px = 1.4em, 16px = 1.6em. For example: ”

```
body {
  font-size: 62.5%; /* font-size 1em = 10px */
}
p {
  font-size: 1.6em; /* 1.6em = 16px */
}
```

“The em is a very useful unit in CSS, since it can adapt automatically to the font that the reader chooses to use.”

- 27: Might be a good time to mention the concept of DRY (Don’t Repeat Yourself). You cover some of these but together they apply to DRY. 

  ie:
  - using inheritance 
  - using classes over id’s
  - using commas to separate multiple selectors and set properties for them at once
  - selector abstraction, ie: if you’re setting multiple classes to the same properties combine them to one class, then if you need to differentiate add a sub-class
  - remembering order in CSS matters!

also:
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

## Day 05: Web Design and Process

### overall:  
- great visuals but some text to compliment would be really helpful. Could be a separate document in the form of notes?
- think this should be split into 2 separate slide shows. One titled “The Web Design Process” and another titled “The Box Model and Positioning with CSS”

### individual slides:
- 10: related: should we explain or at least mention templates that exist already such as bootstrap?
- 12: Maybe use solid colors to show each area? Sort of hard to look at / comprehend if you’ve never heard of the box-model before, especially because borders on elements in websites are usually very thin.
- 13: this diagram is confusing to look at, looks more like it should be used to explain z-index? Not clear from this that margin is not affected by background-color while padding is.
- 15: more elements than just margins use these units, can be applied to other elements with CSS as well
- 19 & 22: think the difference between border and padding would be more easy to see if you also visualized neighboring elements next to the box in the examples. Right now it’s hard to tell the difference between the two visually.
- 31: maybe add the word “flow”? ie: “…and occurs where it normally would in the document flow.”
- 32: mention that the origin in all web layout 0,0 is the top-left corner.
- 35: ended slide show without talking about position: fixed; Explain when / why you would want to use this.









