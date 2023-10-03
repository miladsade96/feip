# CSS

**Explain the 3 main ways to apply css styles to a web page?**  
1. **Inline css**: Using the inline style attribute on an element
```html
<div>
    <p style="color: blue">Hello CSS</p>
</div>
```
2. **Internal css**: Using a style block in the head section of the html file
```html
<head>
    <title>CSS</title>
    <style>
        body {
            font-family: "Andale Mono",serif;
            font-size: 2rem;
        }
    </style>
</head>
```
3. **External css**: Loading an external css file using link tag
```html
<head>
    <title>CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
```

---

**What is css?**  
CSS (Cascading Style Sheets) is a stylesheet language used to describe the presentation of a document written 
in HTML or XML. CSS describes how elements should be rendered on screen, on paper, in speech, or on other media.
CSS is a stylesheet language that controls presentation and styling of HTML and XML content across websites, helping 
create consistent and maintainable design systems. It is an essential web technology.

**How to use variables in sass?**  
Sass allows using variables to store reusable values like colors, fonts, sizes etc. This helps maintain consistent
styling and avoids repetition. Here are some ways to use variables in Sass:

- Define a variable:
```css
$primary-color: #33475b;
```
- Use a variable:
```css 
.header {
  background-color: $primary-color;
}
```
- Variables can store strings, numbers, colors, boolean values, lists etc.
- Variables can be defined within selectors, mixins, functions. Global variables can be defined at the root.
- Assign a variable's value to another variable:
```css
$base-color: #33475b;
$primary-color: $base-color; 
```
- Variables are scoped - they can be overridden locally.
- Use interpolation to combine strings and variables:
```css
$font-size: 1.2em;
p {
  font: #{$font-size}/1.4 Arial; 
}
```
- Default values can be specified using !default:
```css
$primary-color: #33475b !default;
```

---

**explain css sprites and how you would implement them on a page or site?**  
CSS sprites are a technique used to reduce the number of HTTP requests made for image resources on a website.
It works by combining multiple small images into one larger image, and displaying the desired parts of that
image using CSS background positioning.
Here is how to implement CSS sprites:
1. Combine smaller images into one larger sprite image file. Leave some space between images.
2. Define CSS classes for each small image. Set the background image to the sprite image.
3. Use background-position to display the correct part of the sprite image for each class.
For example:

```css
.icon-home {
  background-image: url('sprite.png');
  background-position: 0 0; 
  width: 20px;
  height: 20px;
}

.icon-user {
  background-image: url('sprite.png');
  background-position: -20px 0;
  width: 20px;
  height: 20px;
}
```
4. Reference the icon classes on HTML elements to display the sprite image:
```html
<a class="icon-home"></a>
<a class="icon-user"></a>
```
The advantages of using CSS sprites include:
- Reduces HTTP requests since only one image is loaded instead of multiple
- Improves page load times
- Easier maintenance since all images are in one file
- Common visual style for all icons

---

**Explain the css box model and the layout components that it consists of?**  

The CSS box model is a key concept for controlling layout and design in web pages. Here are the key components
of the CSS box model:
- **Content**: This is the HTML content within an element, such as text, image, or video.
- **Padding**: The transparent space around the content. Padding clears an area around the content and inside the border.
- **Border**: The solid line that surrounds the padding and content. Borders take up space in the layout.
- **Margin**: The transparent space outside the border. Margins create space between elements.

---

**What is a css rule?**  
A CSS rule is a set of styling instructions that applies to specific HTML elements on a web page. It allows
selectively styling parts of the page. The key components of a CSS rule are:
- **Selector**: The HTML element name, id, class etc to target. For example:
  * p: targets all p elements
  * #header: targets id="header"
  * .main: targets all class="main"
- **Declarations**: A list of CSS properties and values in key:value pairs. Goes inside { }.

---

**explain what is an @extend directive used for in sass?**  
The @extend directive in Sass is used to share or inherit CSS properties from one selector to another. It helps
keep CSS code dry and reusable.
For Example:
```scss
// This is the base class
.btn {
  padding: 15px;
  display: inline-block;
  border-radius: 4px;
  color: #fff;
}

// Extend .btn class
.primary-btn {
  @extend .btn;
  background-color: blue;
}

// Extend .btn class
.danger-btn {
  @extend .btn; 
  background-color: red;
}
```

---
**have you played around with the new css flexbox and grid specs?**  
Yes, I have worked quite a bit with CSS Flexbox and Grid and really like the new capabilities they provide for layouts.
Here are some thoughts on my experience:

- **Flexbox**:
  - Makes complex layouts much easier, with the ability to easily align items and distribute space.
  - Axis-based system using flex-direction, justify-content and align-items makes intuitive sense.
  - Flex-wrap to control wrapping is handy for responsive layouts.
  - Ability to easily change ordering of items with order property.
  - Flex-basis, flex-grow, flex-shrink provide fine-grained control over sizing.

- **Grid**:
  - More robust than floats for 2D grid-based layouts. No need for clearing floats.
  - Easy to build complex multi-column responsive layouts with grid-template-columns and grid-template-rows.
  - Grid gap property makes gutter spacing straightforward.
  - Grid areas allow giving memorable names to grid sections.
  - Ability to precisely overlay items with z-index.

---

**What is DOM and how is it linked to css?**  
DOM (Document Object Model) is a programming interface for web documents. It represents the page so that programs 
can change the document structure, style, and content. The DOM represents the document as nodes and objects - making
it easy to modify.
CSS and the DOM are closely linked in several ways:  
- CSS can style various DOM nodes and objects to change their visual styles. For example, CSS can style paragraphs, divs, classes, ids etc.
- Modifying DOM objects in JavaScript can alter their styles. For example, adding/removing CSS classes with JavaScript will change styles.
- DOM methods can directly access and modify CSS styles applied to an element. For example, the element.style property lets you access CSS styles.
- CSS selectors use DOM node names, ids, classes etc to target styling rules to specific elements.
- The DOM getComputedStyle() method returns all the CSS computed styles applied to an element.
- CSS Animations and Transitions use JavaScript DOM methods like getComputedStyle() to access element styles and animate between them.

---

**What is sass?**  
Sass (Syntactically Awesome Style Sheets) is a CSS pre-processor that allows using advanced features like variables,
nesting, mixins, inheritance, etc; which makes writing CSS faster, efficient and maintainable.

---

**Describe floats in css and how they work?**  
Floats in CSS allow elements to be positioned side-by-side rather than stacked vertically. Here's an overview
of how floats work:  
- The float CSS property makes an element float left or right within its container. This takes the element out of the normal document flow.
- Floated elements will move as far left or right as possible within their parent container. Text and inline elements will wrap around the floated element.
- Elements after a floated element will flow around it, filling up available space. This is the primary method of creating multi-column layouts with CSS.
- The clear property can be used to prevent wrapping around floated elements, clearing left/right/both sides.

So in summary, floats make elements wrap and flow around each other, which helps in aligning images, text and creating
multi-column layouts in CSS. They are an essential positioning tool.

---

**What selector nesting in sass is used for?**  
Selector nesting is a feature in Sass that allows nesting CSS selectors to create more organized and readable CSS code.
It helps show the parent-child relationships between HTML elements.
Some ways selector nesting can be useful:
- Can replicate HTML structure to visualize styling relationships:
```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```
- Avoid repetition of parent selectors
```scss
.blog {
  h2 {
    font-size: 2em; 
  }
  
  p {
    color: #333;
  }
}
```
- Write less verbose CSS
```scss
#main {
  color: red;
  
  p {
    color: blue;
  }
}
```
- Create inheritance chains
```scss
.error {
  border: 1px #f00;
  
  .seriousError {
    @extend .error;
    border-width: 3px;
  }
}
```

---

**List out the key features for sass?**  
Here are some of the key features that Sass provides:
- Compatibility - Sass code compiles to valid CSS so works across browsers.
- Variables - For storing reusable values like colors, fonts etc.
- Nesting - For nesting selectors to organize styling and resemble HTML structure.
- Partials and Imports - For modularizing code into separate files that can be imported.
- Mixins - For reusing groups of CSS declarations.
- Extend - For making one selector inherit styles from another.

---

**What is the difference between classes and ids in css?**  
The main differences between classes and IDs in CSS are:
- IDs are unique, more specific, and target single elements.
- Classes are reusable, less specific, and target multiple elements.
- Use classes for common styling needs, IDs for unique or specific element styling.

---

**List out the data types that sass supports?**  
- **Numbers:** Used for any number values
```scss
$size: 18;                  // A number
$px-unit: $size * 1px;      // A pixel measurement
$px-string: $size + px;     // A string
$px-number: $px-unit / 1px; // A number
```
- **Strings:** Used for text values. Can be quoted in single or double quotes
```scss
$website: 'hereismy.site'; // Stores my personal website
$name: 'Milad' + ' Sadeghi';  // 'Milad Sadeghi'
$date:  'Month/Year : ' + 10/2023; // 'Month/Year : 10/2023'
$date:  'Month/Year : ' + (10/2023); 
```
- **Colors:** Used for any color value
```scss
$color: yellowgreen;           // #9ACD32
color: lighten($color, 15%);    // #b8dc70
color: darken($color, 15%);     // #6c9023
color: saturate($color, 15%);   // #a1e01f
color: desaturate($color, 15%); // #93ba45
color: (green + red);           // #ff8000
```
- **Booleans:** Used for true or false values.
```scss
$i-am-true: true;

body {
  @if not $i-am-true {
    background: rgba(255, 0, 0, 0.6);
  } @else {
    background: rgba(0, 0, 255, 0.6); // expected
  }
}
```
- **Null:** Null - is commonly used to define an empty state, neither true or false. This is typically the value you
             want to set when defining a variable without a value, only to prevent the parser from crashing.
```scss
.foo {
  content: type-of(null); // null
  content: type-of(NULL); // string
  $bar: 'foo' + null; // invalid null operation: "foo plus null”.
}
```
- **Lists** Used to store multiple values like 1px 2px 3px. Uses spaces or commas for separation.
```scss
$font-list: 'Raleway','Dosis','Lato'; // Three comma separated elements
$pad-list: 10px 8px 12px; // Three space separated elements
$multi-list: 'Roboto',15px 1.3em; // This multi-list has two lists.
```
- **Maps:** Sass maps are like associative arrays. A map stores both keys and values associated with those keys.
```scss
$styling: (
  'font-family': 'Lato',
  'font-size': 1.5em,
  'color': tomato,
  'background': black
);

h1 {
  color: map-get($styling, 'color');
  background: map-get($styling, 'background');
}
```

----

**What are the differences between sass and scss?**  
Sass and SCSS (Sassy CSS) are two syntax options for the Sass stylesheet language:
- Sass uses the Sass (.sass) syntax which is indented based and does not use braces or semicolons.
```sass
body
  font:
    family: Roboto
    size: 16px
```

- SCSS uses the SCSS (.scss) syntax which is very similar to CSS style with braces and semicolons.
```scss
body {
  font: {
    family: Roboto;
    size: 16px;
  }
}
```

The key differences are:
- Sass uses indentation rather than braces and semicolons. SCSS uses CSS-style syntax.
- Sass files use the .sass extension. SCSS uses .scss extension.
- At a technical level, both compile to the same CSS code. They are just two formats of the same preprocessor.
- SCSS syntax is more popular and widely used because it is easier for developers with CSS experience.

---

**Explain the usage of table-layout in css?**  
The `table-layout` property in CSS is used to specify the algorithm that the browser should use to lay out table cells,
rows, and columns. There are two possible values for this property:
* `auto`: This is the default value, and it allows the browser to use its own algorithm to lay out the table. This
          algorithm typically adjusts the widths of the table and its cells to fit the content.
* `fixed`: This value tells the browser to use a fixed layout algorithm. In this algorithm, the width of each column is
           determined as follows:
  * A `col` element with explicit width sets the width for that column.
  * Otherwise, a cell in the first row with explicit width determines the width for that column.
  * Otherwise, the column gets the width from the shared remaining horizontal space.

The main benefit of using `table-layout: fixed` is that it can improve the performance of rendering tables. This is
because the browser can start rendering the table as soon as it has parsed the first row, even if the content of the
other rows is not yet known.

To use `table-layout: fixed`, you must explicitly set the width of the table using the `width` property. You can also
set the width of individual columns using the `col` element.

Here is an example of a table using `table-layout: fixed`:

```html
<table>
  <colgroup>
    <col width="100px">
    <col width="200px">
  </colgroup>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Cell 1</td>
    <td>Cell 2</td>
  </tr>
  <tr>
    <td>Cell 3</td>
    <td>Cell 4</td>
  </tr>
</table>
```
In this example, the width of the first column is set to 100px and the width of the second column is set to 200px.
This means that the table will always have a width of 300px, regardless of the content of the cells.

---

**what is the difference between a relative, absolute, fixed and static positioned element?**  
The main difference between relative, absolute, fixed, and static positioned elements is how they are positioned
relative to the other elements on the page:
- Static is the default position for all elements. Static elements are positioned in the normal flow of the document,
  meaning that they are stacked on top of each other in the order that they appear in the HTML code.
- Relative elements are positioned relative to their normal position in the document flow. This means that you can use
  the top, right, bottom, and left properties to move the element around its normal position. However, relative elements
  will still take up space in the document flow, meaning that other elements will flow around them.
- Absolute elements are positioned relative to their nearest positioned ancestor. This means that they are removed from
  the normal flow of the document and can overlap other elements. Absolute elements are often used to create popups,
  menus, and other floating elements.
- Fixed elements are positioned relative to the browser viewport, meaning that they stay in the same position on the
  page even when the user scrolls. Fixed elements are often used for navigation bars, headers, and other elements that
  should always be visible to the user.

---

**Have you ever worked with retina graphics? If so, when and what techniques did you use?**  
Yes, I have worked with retina graphics on several occasions. I have used a variety of techniques, including:
* **Using high-resolution images:** For static images, such as logos and icons, I use images that are twice the
                                    resolution of what is needed for non-retina displays. This ensures that the images
                                    look sharp and crisp on retina displays.
* **Using vector graphics:** Vector graphics are scalable images that can be displayed at any resolution without losing 
                             quality. This makes them ideal for use on retina displays.
* **Using CSS media queries:** CSS media queries allow you to specify different styles for different devices and screen
                               resolutions. I use media queries to ensure that my websites and apps look good on both 
                               retina and non-retina displays.

For example, the following CSS code will ensure that the `logo.png` image is displayed at the correct resolution on
both retina and non-retina displays:
```css
img {
  max-width: 100%;
}

@media (-webkit-min-device-pixel-ratio: 2), (min-device-pixel-ratio: 2) {
  img.logo {
    content: url("logo@2x.png");
  }
}
```
This code will display the `logo.png` image on non-retina displays. On retina displays, it will display the 
`logo@2x.png` image, which is a high-resolution version of the logo.

---

**What are the advantages and disadvantages of using css preprocessors?**  
**Advantages of using CSS preprocessors:**
* **More powerful and flexible CSS:** CSS preprocessors like Sass and LESS provide a number of features that are not available in native CSS, such as variables, mixins, functions, and nesting. These features can make your CSS code more maintainable, reusable, and efficient.
* **Reduced code bloat:** CSS preprocessors can help you to reduce the amount of CSS code that you need to write. For example, you can use variables to define common values that can be reused throughout your code. You can also use mixins to create reusable code snippets that can be included in multiple places.
* **Improved CSS organization:** CSS preprocessors can help you to organize your CSS code in a more logical way. For example, you can use Sass's `@use` directive to import CSS files from other Sass files. This can make your code easier to read and understand.
* **Increased productivity:** CSS preprocessors can help you to write CSS code more quickly and efficiently. By using features like variables, mixins, and functions, you can avoid having to repeat yourself and write the same CSS code over and over again.

**Disadvantages of using CSS preprocessors:**
* **Learning curve:** CSS preprocessors can have a bit of a learning curve, especially if you are not familiar with programming concepts like variables and functions. However, there are many resources available online and in books to help you learn CSS preprocessors.
* **Increased build complexity:** CSS preprocessors require an additional build step to compile the preprocessed CSS code into regular CSS code. This can add some additional complexity to your development workflow.
* **Debugging can be more difficult:** Debugging CSS code that has been preprocessed can be more difficult than debugging regular CSS code. This is because the preprocessed CSS code is compiled into a single CSS file, which can make it difficult to track down the source of errors.

---

**How is responsive design different from adaptive design?**  
Responsive design and adaptive design are both approaches to web design that aim to create websites that look good and function well on a variety of devices, from desktop computers to smartphones. However, there are some key differences between the two approaches.
- **Responsive design** is a fluid approach that uses CSS media queries to adjust the layout and appearance of a website based on the screen size of the device it is being viewed on. This means that a single responsive website can be viewed on any device without any major changes to the layout or content.
- **Adaptive design**, on the other hand, uses a fixed layout approach with a different layout for each common device screen size. This means that an adaptive website will have a different layout for desktop computers, tablets, and smartphones.

---
**What is css selectors? name some**  
CSS selectors are used to identify the HTML elements that you want to style. There are a variety of CSS selectors available, each of which targets a different type of HTML element.

Here are some of the most common CSS selectors:

- **Element selector:** This selector selects all elements of a specific type. For example, the div selector selects all div elements on a page.
- **Class selector:** This selector selects all elements with a specific CSS class. For example, the .my-class selector selects all elements with the CSS class my-class.
- **ID selector:** This selector selects all elements with a specific ID. For example, the #my-id selector selects the element with the ID my-id.
- **Descendant selector:** This selector selects all elements that are descendants of a specific element. For example, the div p selector selects all p elements that are descendants of div elements.
- **Child selector:** This selector selects all elements that are direct children of a specific element. For example, the div > p selector selects all p elements that are direct children of div elements.
- **Adjacent sibling selector:** This selector selects all elements that are adjacent siblings of a specific element. For example, the div + p selector selects all p elements that are adjacent siblings of div elements.
- **Pseudo-class selector:** This selector selects elements based on their state, such as whether they are hovered over, focused, or active. For example, the :hover pseudo-class selector selects all elements that are currently being hovered over.

---

**What does accessibility(a11y) mean?**  
Accessibility (a11y) is the practice of making websites, apps, and other digital content accessible to people with disabilities. This includes people who are blind or have low vision, deaf or hard of hearing, have mobility impairments, or have cognitive disabilities.
There are a number of things that can be done to make digital content more accessible. Some common techniques include:
- Providing alternative text for images and videos
- Using clear and concise language
- Avoiding complex layouts and navigation
- Providing captions and transcripts for audio and video content
- Making sure that all content can be accessed using a keyboard

---

**What is css preprocessor and why to use one?**  
A CSS preprocessor is a programming language that extends the capabilities of CSS. CSS preprocessors allow you to use features such as variables, mixins, functions, and nesting to make your CSS code more maintainable, reusable, and efficient.

Here are some of the benefits of using a CSS preprocessor:
- More powerful and flexible CSS: CSS preprocessors provide a number of features that are not available in native CSS, such as variables, mixins, functions, and nesting. These features can make your CSS code more maintainable, reusable, and efficient.
- Reduced code bloat: CSS preprocessors can help you to reduce the amount of CSS code that you need to write. For example, you can use variables to define common values that can be reused throughout your code. You can also use mixins to create reusable code snippets that can be included in multiple places.
- Improved CSS organization: CSS preprocessors can help you to organize your CSS code in a more logical way. For example, you can use Sass's @use directive to import CSS files from other Sass files. This can make your code easier to read and understand.
- Increased productivity: CSS preprocessors can help you to write CSS code more quickly and efficiently. By using features like variables, mixins, and functions, you can avoid having to repeat yourself and write the same CSS code over and over again.

---

**how would you approach fixing browser-specific styling issues?**  
To fix browser-specific styling issues, I would follow these steps:
1. **Identify the issue.** The first step is to identify the browser-specific styling issue. You can do this by inspecting the element in the browser's developer tools. Once you have identified the issue, you can start to troubleshoot it.
2. **Use a CSS reset or normalize.** A CSS reset or normalize CSS file can help to ensure that your website has a consistent appearance across different browsers by resetting or normalizing the default styles applied to elements.
3. **Use vendor prefixes.** Vendor prefixes are special styles that are used to add support for certain CSS properties in specific browsers. For example, you might use the `-webkit-` prefix to add support for the `flex` property in Chrome and Safari.
4. **Use feature detection.** Instead of relying on specific browser prefixes, you can use feature detection to determine whether a particular feature is supported in the user's browser.
5. **Test your code.** Once you have made changes to your CSS code, it is important to test it on different browsers to make sure that it is rendering correctly.

Here are some additional tips for fixing browser-specific styling issues:
* Use a browser compatibility testing service such as BrowserStack or Sauce Labs to test your website on a variety of browsers and devices.
* Use a CSS linter such as ESLint or Stylelint to check your CSS code for errors and potential browser compatibility issues.
* Keep up with the latest CSS standards and browser updates.

---

**what is the difference between resetting and normalizing css? which would you choose, and why?**  
- **Resetting CSS** is a CSS file that removes all the default browser styles applied to elements. This can be useful for ensuring that your website has a consistent appearance across different browsers, but it can also be time-consuming and error-prone to maintain.

- **Normalizing CSS** is a CSS file that normalizes the default browser styles applied to elements. This means that it keeps some of the useful default styles and only removes the ones that are inconsistent or unnecessary. Normalizing CSS is generally considered to be a better approach than resetting CSS, as it is easier to maintain and less likely to cause unexpected problems.

**Which one would I choose?** I would choose to normalize CSS. It is a more modern and efficient approach that is easier to maintain and less likely to cause unexpected problems.

Here are some additional benefits of using normalize CSS:

* It can help to improve the performance of your website, as browsers do not have to waste time rendering default styles.
* It can make your CSS code more readable and maintainable, as you do not have to worry about overriding default browser styles.
* It can help to improve the accessibility of your website, as it ensures that all elements have a consistent appearance and functionality across different browsers.

---

**explain the understanding of the box model and how you would tell the browser in css to render your layout in different box model?**  
The CSS box model is a way of understanding how HTML elements are displayed on a web page. Each HTML element is represented as a box, which has four parts: the content box, padding, border, and margin.

* **Content box:** This is the area where the text and images of the element are displayed.
* **Padding:** This is a transparent area that surrounds the content box.
* **Border:** This is a line that surrounds the padding and content box.
* **Margin:** This is a transparent area that surrounds the border.

The box model can be used to control the size and position of HTML elements on a web page. You can use CSS properties such as `width`, `height`, `padding`, `border`, and `margin` to control the different parts of the box model.

**To tell the browser to render your layout in a different box model, you can use the `box-sizing` CSS property.** This property can be set to `content-box` or `border-box`.

* **Content-box:** This is the default value for the `box-sizing` property. When it is set to `content-box`, the width and height of the element will only include the content box. The padding, border, and margin will be added to the width and height of the element.
* **Border-box:** When the `box-sizing` property is set to `border-box`, the width and height of the element will include the padding, border, and margin. This can make it easier to calculate the total size of an element and its contents.

---

**Describe pseudo-elements and discuss what they are used for?**  

Pseudo-elements are a CSS feature that allows you to style specific parts of an element without having to create a new element.
Pseudo-elements are denoted by a double colon (::) followed by a keyword. For example, the ::first-letter pseudo-element targets
the first letter of an element.

Pseudo-elements can be used for a variety of purposes, such as:
- Styling the first line of a paragraph
- Adding a drop cap to the first letter of a paragraph
- Styling the first letter of a heading
- Styling the before and after content of an element
- Styling the selection cursor
- Styling the scrollbar of an element

---
