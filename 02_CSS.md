# Cascading Style Sheets

## Introduction
* Why CSS?
* Syntax
  - Selector { property1: value; property2: value; }
  - Example: p { color: blue; text-align: center; }
* External, Internal, Inline
  - Styles are specified in separate file (eg. **style.css**)
  - The file is included in the head section of html page using **link** tag
  - &lt;link rel="stylesheet" type="text/css" href="style.css"&gt;
  
## CSS Selectors
* The **element** selector
  - p { color: blue; text-align: center; }
  - Selecting body tag impacts the entire page
  - body { background-color: gray; }
* The **id** selector
  - &lt;p id="first"&gt; This is used to demonstrate id selector.&lt;/p&gt;
  - #first { text-align: right; }
* The **class** selector
  - &lt;p class="group"&gt; This is used to demonstrate class selector.&lt;/p&gt;
  - &lt;p class="group"&gt; Unlike id, same class name can be used to select multiple elements.&lt;/p&gt;
  - .group { color: blue; }
* Multi class selector
  - Same html element can be part of multiple classes
  - &lt;p class="first second"&gt;This is used to demonstrate class selector.&lt;/p&gt;
  - .first { color: blue; }
  - .second { text-align: center; }
* Element and class combo selector
  - p.intro { color: blue; text-align: center; }
* The * selector (universal selector)
  - Applies to all elements of the HTML page
  - Doesn't override id's though
  - &star; { text-align: center; color=blue; }
* Grouping multiple selectors
  - h1, p, li { color: blue; text-align: center; }
* Adjacent siblings
  - h3 + ul { border: 4px dotted purple; }

```css
body { 
  /* background-color: gray; */
  background: url(https://i.itworldcanada.com/wp-content/uploads/2020/04/f3ff9r3ie2w-768x609.png)
}

div {
  background-color: blue;
  border-color: red;
  border-width: thick;  /* 2px */
  border-style: dotted;
}

p { color: yellow; }

span {
  background-color: red;
  color: black;
  text-decoration: underline; /* overline, linethrough, etc. */
}

h3 + ul { border: 4px dotted purple; } // Apply to ul next to h3

li a { color: red; }

li a[href="https://www.google.co.in"] { 
  color: blue; 
  border: 5px solid orange;
}
```

## Specificity
Defines the hierarchy of CSS styling and what type of tags overrule the others.

```html
<ul>
  <li class="topitems">First</li>
  <li id="two" class="topitems">Second</li>
  <li>Third</li>
  <li>Fourth</li>
</ul>
```

```css
li { color:red; }

.topitems {color:blue; }

#two { border:3px solid black; }
```

## Resources
* [MDN CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* Google Inspector
