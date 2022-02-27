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
  - &star; { text-align: center; color=blue; }
* Grouping multiple selectors
  - h1, p, li { color: blue; text-align: center; }
