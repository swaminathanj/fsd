# Hyper Text Markup Language (HTML)

## A basic bare-bones HTML page

* Structure of a HTML page
  - Set doctype
  - The **&lt;html&gt;** tag
  - The **&lt;head&gt;** tag
  - The **&lt;meta&gt;** tag with **charset** attribute
  - The **&lt;title&gt;** tag
  - The **&lt;body&gt;** tag

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>
    
  </body>
</html>
```

## Different levels of headings

Heading tags are used inside &lt;body&gt; section.

* Heading tags
  - The **&lt;h1&gt;** tag
  - The **&lt;h2&gt;** tag
  - The **&lt;h3&gt;** tag
  - The **&lt;h4&gt;** tag
  - The **&lt;h5&gt;** tag

```html
<h1>First level heading</h1>

<h2>Second level heading</h2>

<h3>Third level heading</h3>

<h4>Fourth level heading</h4>
```

## Writing text and formatting

These tags are used within &lt;body&gt; section.

* Writing and formatting text
  - The **&lt;p&gt;** (paragraph) tag
  - The **&lt;p&gt;** tag with **align** attribute set to "right" or "center"
  - The **&lt;strong&gt;** (bold) tag
  - The **&lt;em&gt;** (emphasis/italics) tag
  - The **&lt;span&gt;** tag
  - The **&lt;span&gt;** tag with **style** attribute **text-decoration** field for **underline**
  - The **&lt;span&gt;** tag with **style** attribute for **color**
  - The **&lt;sup&gt;** tag (superscript)
  - The **&lt;sub&gt;** tag (subscript)
  - The **&lt;br /&gt;** (line break) tag
  - The **&lt;hr /&gt;** (horizontal ruler) tag
  - The **&lt;ol&gt;** (ordered list) tag
  - The **&lt;ul&gt;** (unordered list) tag
  - The **&lt;li&gt;** (list item) tag
  - The **&lt;details&gt;** and **&lt;summary&gt;** tags - To hide/show text

```html
<p>Free flowing paragraph text are enclosed within the paragraph tag. You use <br /> for line break. Adding bullets can be done using <ul> and <li> tags as shown below.</p>
<ul>
  <li>This is how you make the <strong>text bold</strong>.</li> 
  <li>This is how you make the <emph>text italic</emph>.</li>
  <li>The underlining is not so simple.</li>
</ul>

<p style="color:red">Any part of the <span style="color:blue">text can be made blue</span> by enclosing them within span tag and using the style attribute.
In fact, the entire paragraph can be set to red color by using style attribute of the paragraph tag.
You can also <span style="text-decoration: underline";>underline text</span> using style tag.</p>

<p>You can also create numbered bullets by using ol and li tags.</p>
<ol>
  <li>ol refers to ordered list</li>
  <li>li refers to list item</li>
  <li>ul refers to unordered list</li>
  <li>You can also have nested lists.
    <ul>
      <li>This is first sub-item of the fourth item</li>
      <li style="color: cyan">The subitem can be colored in a similar way.</li>
    </ul>
  </li>
</ol>

<details><summary>This is how text can be converted to <sup>superscript</sup> and <sub>subscript</sub>.</summary> 
  For example, the equation of a circle can be written as x<sup>2</sup> + y<sup>2</sup> = r<sup>2</sup>.</details>
```

## Symbols

Symbols are used in the &lt;body&gt; tag. A list of commonly used symbols are provide below. This is only a small subet of the overall set of symbols.

* Symbols
  - **&amp;nbsp;** - non breaking space
  - **&amp;#x20B9;** - Indian Rupee symbol
  - **&amp;quot;** - Double quote
  - **&amp;apos;** - Single quote
  - **&amp;check;** - Check mark &check;
  - **&amp;plus;** - plus symbol
  - **&amp;minus;** - minus symbol
  - **&amp;times;** - multiplication symbol
  - **&amp;divide;** - division symbol
  - **&amp;equals;** - equals symbol
  - **&amp;ne;** - not equals symbol
  - **&amp;frac12;** - &frac12; symbol
  - **&amp;frac14;** - &frac14; symbol
  - **&amp;frac23;** - &frac34; symbol

```html

```

## Hyperlinks

<p>Hyperlinks are used in every part of the page. Both in the &lt;head&gt; and &lt;body&gt; sections.</p>

* Hyperlinks
  - The **&lt;a&gt;** tag
  - The **href** attribute
  - The **target** attribute with **"_blank"** value
  - The **rel** attribute
 
 ```html
 
 ```

## Image

* Image
  - The **&lt;img&gt;** tag
  - The **src** attribute
  - The **alt** attribute
  - The **height** attribute
  - The **width** attribute
  - The **&lt;figure&gt;** tag
  - The **&lt;figcaption&gt;** tag

```html

```

## Audio and Video

* Audio
  - The **&lt;audio&gt;** tag
  - The **&lt;audio&gt;** tag with **src** and **controls** attributes
  - The **&lt;source&gt;** tag inside audio tag with **src** and **type**
  - The **autoplay** attribute
* Video
  - The **&lt;video&gt;** tag
  - The **&lt;video&gt;** tag with **src**, **width**, **height** and **controls** attributes
  - The **&lt;source&gt;** tag inside video tag with **src** and **type**
  - The **autoplay** attribute

```html

```

## Table

* Tables
  - The **&lt;table&gt;** tag
  - The **&lt;thead&gt;** tag
  - The **&lt;tr&gt;** tag
  - The **&lt;td&gt;** tag
  - The **&lt;tfoot&gt;** tag
  - The **&lt;caption&gt;** tag

```html

```

## Block tags

These tags are used within the &lt;body&gt; section. 

* Block tags ([Reference](https://softcodeon.com/tutorials/10-alternatives-to-the-div-html-tag.htm))
  - The **&lt;header&gt;** tag
  - The **&lt;nav&gt;** tag
  - The **&lt;article&gt;** tag
  - The **&lt;section&gt;** tag
  - The **&lt;figure&gt;** tag
  - The **&lt;aside&gt;** tag
  - The **&lt;div&gt;** tag
  - The **&lt;footer&gt;** tag
  - The **&lt;blockquote&gt;** tag
  - The **&lt;mark&gt;** tag

```html

```

## User Interface

These tags are used within &lt;body&gt; section. They need additional work towards handling user events and inputs which will be dealt later when Java Script is introduced.

* UI tags
  - The **&lt;button&gt;** tag
  - The **&lt;label&gt;** tag
  - The **&lt;input&gt;** tag with **type** attribute set to **"text"** (text box)
  - The **&lt;input&gt;** tag with **type** attribute set to **"password"** (password)
  - The **&lt;input&gt;** tag with **type** attribute set to **"radio"** (radiobutton) - to be followed by a label
    - Bunch of radiobuttons are grouped by **name** attribute
  - The **&lt;input&gt;** tag with **type** attribute set to **"checkbox"** (checkbox) - to be followed by a label
    - Bunch of radiobuttons are grouped by **name** attribute
  - The **&lt;select&gt;** tag 
  - The **&lt;option&gt;** tag enclosed within **&lt;select&gt;** tag
  - The **&lt;meter&gt;** tag with **value**, **min** and **max** attributes
  - The **&lt;progress&gt;** tag with **value** and **max** attributes

```html
<label>Label</label>
<input type="text">
<input type="password">
<button>Button</button>
<select> </select>
<select>
  <option>Value 1</option>
  <option>Value 2</option>
</select>
<br />
<input type="radio">
<label>option 1</label>
<input type="checkbox">
<label>option 1</label>
```

