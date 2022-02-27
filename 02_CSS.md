# Cascading Style Sheets

## Introduction
* Why CSS?
* External, Internal, Inline
* Syntax
  - Selector { property1: value; property2: value; }
  - Example: p { color: blue; text-align: center; }
  
## CSS Selectors
* The **element** selector
  - p { color: blue; text-align: center; }
* The **id** selector
  - &lt;p id="first"&gt; This is used to demonstrate id selector.</p>
  - #first { text-align: right; }
*  The **class** selector
  - &lt;p class="group"&gt; This is used to demonstrate class selector.</p>
  - &lt;p class="group"&gt; Unlike id, same class name can be used to select multiple elements.</p>
  - .group { color: blue; }
* Multi class selector
  - Same html element can be part of multiple classes
  - &lt;p class="first second"&gt;This is used to demonstrate class selector.</p>
  - .first { color: blue; }
  - .second { text-align: center; }
* The * selector (universal selector)
  - Applies to all elements of the HTML page
  - * { text-align: center; color=blue; }
