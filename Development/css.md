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
