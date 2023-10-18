# HTML

**What is an iframe and how it works?**  
An iframe (inline frame) is an HTML document embedded inside another HTML document on a website. It allows you to
display another webpage within the current webpage.
```html
<iframe src="https://www.example.com" width="600" height="400"></iframe>
```

---

**Explain meta tags in html?**  
Meta tags provide metadata and information about a web page. They are not visible to users but are machine-readable.
meta tags provide structured data about the page content in a machine readable way, which is used by browsers, search
engines, social media to display and index pages properly. The most common ones are charset, description, keywords and
social meta tags.
```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Free Web tutorials">
  <meta name="keywords" content="HTML, CSS, JavaScript">
  <meta name="author" content="John Doe">
</head>
```

---

**What is the purpose of alt attribute on images?**  
The main purposes of alt text are to provide accessibility, improve SEO, and present context for an image to both
sighted and non-sighted users. Alt text is important for images that convey meaning and content.

---

**What is the difference between span and div?**  
`<span>` is inline, non-breaking, content grouping container while `<div>` is block-level, creates structure breaks,
visual/layout grouping container.

---

**How can I get indexed better by search engines?**  
It is possible to get indexed better by placing the following two statements in the <HEAD> part of your documents:
```html
<meta NAME="keywords" CONTENT="keyword1 keyword2 keyword3">
<meta NAME="description" CONTENT="This is the description of the site.">
```
Both may contain up to 1022 characters. If a keyword is used more than 7 times, the keywords tag will be ignored
altogether. Also, you cannot put markup (other than entities) in the description or keywords list.

---

**What are some of the key goals and motivations for the html5 specification?**  
Here are some of the key goals and motivations behind the HTML5 specification:
- Semantic markup - Provide more descriptive HTML tags like `<header>`, `<footer>`, `<article>` etc. to better represent
  different content types. Help search engines understand the structure.
- Multimedia support - With HTML5 `<video>` and `<audio>` tags, native multimedia playback support without plugins.
- Connectivity - Features like WebSockets allow two-way communication between a browser and server for real-time apps.
- Offline storage - localStorage API allows web apps to store data locally in the browser and work offline.
- Hardware access - Browsers can access user hardware like camera, GPS, accelerometer using HTML5 APIs. Enables immersive web experiences.
- Device agnostic - Design websites/apps for any device like mobile, tablet, desktop. Meta tag for responsive design.
- Accessibility - ensures semantics and APIs consider disabilities and accessibility needs.

---

**How can I highlight text in html?**  
Using the `<mark>` tag:
```html
<p>Here is some <mark>highlighted text</mark> in a paragraph.</p>
```

- Using CSS:
```html
<p>This text is <span class="highlight">highlighted</span> with CSS.</p>

<style>
.highlight {
  background-color: yellow;
}
</style>
```

- Using JavaScript:
```js
// select element 
const text = document.getElementById("text");

// apply highlight
text.style.backgroundColor = "yellow"; 
```

---

**Briefly describe the correct usage of the following html5 semantic elements: `<header>` , `<article>` , `<section>` , `<footer>`?**  

- `<header>` - Represents a header section for the nearest section or the overall page. Typically, contains heading 
             elements, logo, introductory content. Goes inside `<body>`.
- `<article>` - Represents a self-contained content piece like a blog post, news article, user-submitted comment.
                Can have its own `<header>` and other semantic elements.
- `<section>` - Groups thematically related content together. Can contain headings, paragraphs, images etc. Used to
                divide up page content into meaningful sections.
- `<footer>` - Contains meta information about the nearest `<article>` or `<section>` element. Typically, has author, 
               copyright, related links.

Usage guidelines:  
- `<header>` and `<footer>` appear at the start/end of `<article>`, `<section>`, `<body>`.
- `<article>` is for standalone content pieces that make sense on their own.
- `<section>` splits up content in thematic groups. Don't overuse it.
- Multiple `<article>` elements can reside in a `<section>` and vice versa.

---

**What is character encoding in html?**  
Character encoding defines how text is represented digitally. Declaring the encoding helps avoid errors in text
interpretation and ensures multilingual support. `UTF-8` is the standard encoding for HTML pages.

---

**What is a self-closing tag?**  
A self-closing tag in HTML is a tag that does not require a separate closing tag. Some examples of self-closing tags:
- `<br>` - Adds a line break
- `<hr>` - Adds a horizontal line 
- `<img>` - Adds an image
- `<input>` - Defines an input field
- `<link>` - Defines a link to an external resource 
- `<meta>` - Defines metadata about the HTML document

To denote a tag is self-closing, a `/` is added before the final `>` of the opening tag. For example:
```html
<br />
<img src="image.jpg" />
```

---

**What is the difference between an attribute and a property in html?**  
The main differences between attributes and properties in HTML are:

- **Attributes**:  
  - Defined in HTML tags to provide additional information about elements
  - Provided as `name/value` pairs like `<a href="url">`
  - Attribute names and values are case-insensitive, e.g `<a href="Url">`
  - Values must be enclosed in quotes
  - Do not change after being set
  - Can only be accessed and updated via DOM methods

- **Properties**:  
  - Represent specific characteristics of DOM elements
  - Accessed via DOM properties like element.property
  - Names are case-sensitive
  - No quotes required for values
  - Can dynamically change via JavaScript
  - Reflect the current state of an element

---

**When is it appropriate to use the small element?**  
The `<small>` element in HTML is used to represent side-comments and small print, like disclaimers, caveats, 
legal restrictions, etc. Some common appropriate uses of the `<small>` element:
- Copyright information in the page footer:
```html
<small>© 2023 MyWebsite. All rights reserved.</small>
```
- Terms and conditions or disclaimers stating legal or other restrictions:
```html
<small>Prices subject to change without notice.</small>
```
- Fine print for citing sources or providing attributions:
```html
<small>Data source: ACME Research</small>
```
- De-emphasizing or offsetting secondary text like asides and advisory notes:
```html
<p>Best deals this week on headphones. <small>While supplies last.</small></p>
```

---

**Explain the differences between block elements and inline elements?**  
The main differences between block elements and inline elements in HTML are:
- **Block Elements:**
  - Take up the full width available by default
  - Force a line break before and after itself
  - Can set height and width values
  - Can have margins and paddings adjusted
  - Common block elements: `<div>`, `<p>`, `<h1>-<h6>`, `<form>`

- **Inline Elements:**
  - Take up only the required width as per content
  - Do not force line breaks before or after
  - Cannot have fixed height and width
  - Horizontal margins and paddings only are applied
  - Common inline elements: `<span>`, `<a>`, `<img>`, `<strong>`


So in summary:
- Block elements consume full horizontal space and break the flow
- Inline elements consume only the needed width and don't break flow

---

**Explain almost standard, full standard and quirks mode in html?**  
Browsers can render web pages in different modes based on the presence and validity of the document type declaration
in HTML code. The three main rendering modes are:

1. Quirks Mode:
   - Browser renders page using an older box model and non-standard behavior.
   - Triggered when there is no doctype or invalid doctype.
   - Causes layout inconsistencies across browsers.
   - Should be avoided for web pages.

2. Almost Standards Mode:
   - Browser uses some error forgiveness and backward compatibility.
   - Triggered by older, transitional doctypes like HTML 4.01 Transitional.
   - May cause small quirks in layout across browsers.

3. Full Standards Mode:
   - Browser adheres strictly to HTML and CSS standards.
   - Triggered by HTML5 doctype `<!DOCTYPE html>`
   - Ensures consistent rendering across updated browsers.
   - Is the recommended mode for modern web pages.

Web pages should use the HTML5 doctype `<!DOCTYPE html>` to trigger full standards mode in browsers. This ensures
predictable and consistent rendering based on web standards.

---