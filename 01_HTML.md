# Hyper Text Markup Language (HTML)

## A basic bare-bones HTML page

The following tags are part of every HTML page and define the structure of the page.

- Set doctype
- The **&lt;html&gt;** tag
- The **&lt;head&gt;** tag
- The **&lt;meta&gt;** tag with **charset** attribute
- The **&lt;title&gt;** tag
- The **&lt;body&gt;** tag
- **&lt;!-- --&gt;**

Here is the basic bare-bones html page which does or displays almost nothing.

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>
    <!-- This is a comment -->
  </body>
</html>
```

## Different levels of headings

Heading tags are used inside &lt;body&gt; section.

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

These tags are used within &lt;body&gt; section. These are the frequenctly used elements of the content.

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

Symbols are used in the &lt;body&gt; section. A list of commonly used symbols are provide below. This is only a small subet of the overall set of symbols.

- **&amp;nbsp;** - non breaking space (&nbsp;)   Note: Parenthesis are used to show the effect of the tag
- **&amp;#x20B9;** - Indian Rupee symbol &#x20B9;
- **&amp;quot;** - Double quote &quot;
- **&amp;apos;** - Single quote &apos;
- **&amp;check;** - Check mark &check;
- **&amp;plus;** - plus symbol &plus;
- **&amp;minus;** - minus symbol &minus;
- **&amp;times;** - multiplication symbol &times;
- **&amp;divide;** - division symbol &divide;
- **&amp;equals;** - equals symbol &equals;
- **&amp;ne;** - not equals symbol &ne;
- **&amp;frac12;** - &frac12; symbol &frac12;
- **&amp;frac14;** - &frac14; symbol &frac14;
- **&amp;frac23;** - &frac34; symbol &frac23;

## Hyperlinks

Hyperlinks are used in every part of the page. They take you to another related page. They appear in &lt;body&gt; section and can appear in &lt;head&gt; too.

- The **&lt;a&gt;** tag
- The **href** attribute
- The **target** attribute with **"_blank"** value
 
 ```html
<a>Google</a> (not hyperlinked)
<a href="https://www.google.co.in">Google</a> (hyperlinked and when clicked, opens in this tab)
<a href="https://www.google.co.in" target="_blank">Google</a> (hyperlinked and when clicked, opens in a new tab)
<a href="https://www.google.co.in" target="_self">Google</a> (opens in this tab - explicitly stated)
 ```

## Image

Image tag is used to display an image. It can be wrapped inside figure block and provide caption. Image tags appear in both &lt;body&gt; and &lt;head&gt; sections.

- The **&lt;img&gt;** tag
- The **src** attribute
- The **alt** attribute
- The **height** attribute
- The **width** attribute
- The **&lt;figure&gt;** tag
- The **&lt;figcaption&gt;** tag

```html
<figure>
  <img src="photo.jpg" width="10%" alt="A beautiful garden">
  <figcaption>Scenary</figcaption>
</figure>
```

## Audio and Video

Audio and video tags are specified are used to show audio and video respectively. They are typically used in &lt;body&gt; section. For these tags to really play audio/video, necessary software must be installed and supported in the system and browser.

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
<audio src="audio.mp3" controls>Sample Audio</audio>
<audio controls>Play list
  <source src="audio.mp3" type="audio/mp3">
  <source src="audio.ogg" type="audio/ogg">
  <p>Cannot play! Your browser doesn't support the audio formats.</p>
</audio>

<video src="video.mp4" width="400" controls>Sample Video</audio>
<video controls>Play list
  <source src="video.mp4" width="400" type="video/mp4">
  <source src="video.webm" width="400" type="video/webm">
  <p>Cannot play! Your browser doesn't support the video formats.</p>
</video>
```

## Table

Table tags are used to display data in a tabular format. Usually appears in &lt;body&gt; section. The tags also provides attributes that allows cells to span multiple rows and columns.

- The **&lt;table&gt;** tag
- The **&lt;th&gt;** tag
- The **&lt;tr&gt;** tag
- The **&lt;td&gt;** tag
- The **&lt;td&gt;** tag with **colspan** and **rowspan** attributes.
- The **&lt;caption&gt;** tag

```html
<table border="1">
  <tr>
    <th>Column1</th>
    <th>Column2</th>
    <th>Column3</th>
  </tr>
  <tr>
    <td>one</td>
    <td colspan="2">two and three</td>
  </tr>
  <tr>
    <td rowspan="2">four and seven</td>
    <td>five</td>
    <td>six</td>
  </tr>
  <tr>
    <td>eight</td>
    <td>nine</td>
  </tr>
  <caption>A table demonstration</caption>
</table>
```

## Block tags

These tags are used within the &lt;body&gt; section for dividing the page into separate sections. 

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

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>HTML5</title>
  </head>
  <body>
    <header>
      <h1>HTML 5</h1>
    </header>
    <nav>
      <ul>
        <li>Topic 1</li>
        <li>Topic 2</li>
        <li>Topic 3</li>
      </ul>
    </nav>
    <section>
      <h2>Section</h2>
      <article>
        <h2>Article 1</h2>
        <p>This is article 1</p>
      </article>
      <article>
        <h2>Article 2</h2>
        <p>This is article 2</p>
      </article>
    </section>
    <footer>
      <p>For any queries please mail me</p>
    </footer>
  </body>
</html>
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
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Sample Form</title>
  </head>
  <body>
  	<h1>A Sample HTML Form</h1>
    <form>
      <label>Username</label>
      <input type="text"><br>

      <label>Password</label>
      <input type="password"> <br>

      <label>Age</label>
      <select>
        <option>0 - 18 years</option>
        <option>18 - 40 years</option>
        <option>41 - 65 years</option>
        <option>65+ years</option>    
      </select> <br>

      <label for="birthday">Date of Birth</label>
      <input type="date"> <br>

      <label>Gender</label>
      <input type="radio" name="gender">
      <label>Male</label>
      <input type="radio" name="gender">
      <label>Female</label> <br>

      <label>Interests</label>
      <input type="checkbox">
      <label>Sports</label>
      <input type="checkbox">
      <label>Music</label>
      <input type="checkbox">
      <label>Travel</label>
    </form>
  </body>
</html>
```

