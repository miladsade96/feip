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

**How can I get indexed better by search engines?**  
It is possible to get indexed better by placing the following two statements in the <HEAD> part of your documents:
```html
<meta NAME="keywords" CONTENT="keyword1 keyword2 keyword3">
<meta NAME="description" CONTENT="This is the description of the site.">
```
Both may contain up to 1022 characters. If a keyword is used more than 7 times, the keywords tag will be ignored
altogether. Also, you cannot put markup (other than entities) in the description or keywords list.

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

**How do you set IE compatibility mode?**  
Here are a few ways to set IE compatibility mode in HTML pages:
- Add a meta tag to the head section of your HTML:
```html
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```
- Use HTTP headers to force IE to render pages in the highest mode available:
```
X-UA-Compatible: IE=edge
```
- Add a command line parameter if opening the page locally in IE:
```
iexplore.exe -c "IE=EmulateIE7"
```
- Use the X-UA-Compatible attribute in the opening <html> tag:
```html
<html xmlns="http://www.w3.org/1999/xhtml" x-ua-compatible="IE=EmulateIE7">
```
- Set a registry key on the client machine to always use a specific version:
```
HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\Main\FeatureControl\FEATURE_BROWSER_EMULATION
```
The meta tag or HTTP header methods are the easiest and most reliable ways to force IE compatibility mode across all
clients. The version number can also be changed to emulate different versions of IE.

---

**What is an optional tag?**  
An optional tag in HTML refers to a tag that doesn't require a corresponding closing tag. The closing tag is optional
for these HTML elements. Some common optional tags in HTML include:
- `<img>` - The image tag is always a single self-closing tag.
- `<br>` - The line break tag.
- `<hr>` - The horizontal rule tag.
- `<input>` - The input tag for forms.

---

**Have you used different HTML templating language before?**  
Yes, I have experience with `JSX` HTML templating language. `React/JSX` is not a typical templating language but `JSX`
is a JavaScript extension that allows writing HTML templates within JavaScript code which promotes reusable UI components.

---

**How do you change the direction of html text?**  
There are a few different ways to change the text direction in HTML:
1. Use the `dir` attribute:
```html
<p dir="rtl">This text will go right to left</p>
```
The dir attribute can be set to "rtl" for right-to-left text or "ltr" for left-to-right.
2. Use the `bdo` tag:
```html
<bdo dir="rtl">This text will also go right to left</bdo>
```
3. Set the `direction` CSS property:
```css
p {
  direction: rtl;
}
```
4. Set the `lang` attribute on the HTML tag:
```html
<html lang="ar">
```
This will make right-to-left text automatic for languages like Arabic.

---

**What are defer and async attributes on a `<script>` tag?**  
The defer and async attributes on a `<script>` tag control when the script should be executed when loading a web page:
- **defer** - This attribute tells the browser to only execute the script file once the HTML document has been fully
  parsed. The script is executed in order, before the DOMContentLoaded event.
- **async** - This attribute allows the script to be executed asynchronously as soon as it is available, without
  blocking page rendering. The script may be executed before the HTML document is fully parsed. Multiple
  async scripts may not execute in a predictable order.

The key differences are:
- defer scripts are executed in order, async scripts can be executed in any order.
- defer scripts will delay the DOMContentLoaded event, async scripts will not.
- async scripts do not block page rendering, defer and normal scripts do.

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

**How do you serve a page with content in multiple languages?**  
Here are some common ways to serve a page with content in multiple languages:
- Build separate pages for each language and serve them based on the user's language preference, detected via browser settings or user selection. Eg: page.html, page-fr.html, page-es.html
- Use content negotiation via the Accept-Language header to serve different language versions based on the header value. The server can detect the preferred language and serve the appropriate content.
- Implement internationalization where string constants are stored in resource bundles based on language. The appropriate resource file can be served dynamically based on user's locale.
- Maintain strings/translations in a database and query/substitute them dynamically via a server side script when serving the page.
- Use client side translation by sending a single neutral language page and translating it to user's language via JavaScript by looking up strings in a JSON/XML dictionary.
- Maintain translations in a key-value JSON object and interpolate values dynamically on page render via a template engine like Handlebars.
- For static content, maintain multiple copies of pages and links to language alternatives using the lang attribute and hreflang tag.

The best approach depends on the application architecture, whether it is server side or client side rendered, if the
languages are known upfront or dynamic etc. A combination of static content, dynamic substitution and client side
translation often works best.

---

**What is new in HTML5?**  
Here are some of the major new features and improvements in HTML5:
- Semantic elements like `<header>`, `<footer>`, `<article>`, `<section>` etc. This gives better document structure and meaning.
- Canvas for 2D drawing. Allows for dynamic, scriptable rendering of 2D shapes and bitmap images.
- Video and audio support without plugins. Allows for embedding video and audio files natively in webpages.
- Local storage for client side data storage. Allows web apps to store data on the client side.
- Web workers for background processing. Allows js code to run in background threads.
- Geolocation API for location detection. Allows webapps to access user's location.
- Drag and drop API. Allows for native drag and drop of elements.

---

**What is the difference between `<section>` and `<div>`?**  
The `<section>` and `<div>` tags are both used to group content in HTML, but have some differences:
- `<div>` is a generic container element that has no semantic meaning. It is used to group content for styling purposes only.
- `<section>` is a thematic grouping element that is used to group related content. It has semantic meaning as it
represents a section of a document.

Some key differences:
- `<section>` can have a heading (`<h1>-<h6>`) to represent the topic of the content. `<div>` cannot.
- `<section>` content should be related and have a common theme. `<div>` is just a generic wrapper.
- Multiple <section> elements can be nested to create an outline of the document. `<div>` cannot do this.
- Screen readers can identify `<section>` tags for accessibility purposes. `<div>` has no special meaning.
- `<article>` tags should go inside `<section>` tags if relevant. `<div>` cannot contain `<article>`.

---

**Where and why is the rel="noopener" attribute used?**  
The `rel="noopener"` attribute is used on anchor (`<a>`) tags when linking to external websites to prevent tab nabbing.
For example:
```html
<a href="http://example.com" target="_blank" rel="noopener">Example Site</a>
```
The reason it is used is that when you use `target="_blank"` on a link, it opens the destination URL in a new browser tab.
This allows the target destination to access the `window.opener` property and potentially redirect the opening tab to a
malicious site using JavaScript code. Adding `rel="noopener"` prevents the newly opened page from being able to access
`window.opener`. This stops potential tab nabbing or redirection from the external site.

---

**Can a webpage contain multiple `<haeder>` elements? What about `<footer>` elements?**  
Yes, a webpage can contain multiple `<header>` and `<footer>` elements:
- `<header>` - Represents an introductory content block. There can be one `<header>` per section or document. For example:
```html
<header>
  <!-- page header -->
</header>

<section>

  <header>
    <!-- section header -->
  </header>
  
  <!-- section content -->
  
</section>
```

- `<footer>` - Represents a closing or end content block. There can be one `<footer>` per section or document. For example:
```html  
<footer>
  <!-- page footer --> 
</footer>

<section>

  <!-- section content -->

  <footer>
   <!-- section footer -->
  </footer>
  
</section>
```

---

**What is webSQL?**  
WebSQL is a web-based database API that allowed browsers to store data locally on the client-side. WebSQL provided a
simple SQL-based interface for apps to store structured data locally on the client-side. But due to lack of standards,
IndexedDB has replaced it as the preferred option for local storage in browsers today.

---

**What is the DOM?**  
The DOM (Document Object Model) is an API that represents and interacts with HTML, XML or SVG documents. It provides
a structural representation of the document as a tree of nodes and defines methods to access and manipulate each node.

---

**What is HTML5 web storage? Explain localStorage and sessionStorage.**  
HTML5 introduced two new storage APIs - `localStorage` and `sessionStorage` - that allow websites to store data
client-side, in the user's browser. `localStorage` allows saving `key/value` pairs persistently in the browser. The
data does not expire, is available across browser sessions and persists when the browser is closed or reopened on the
client machine.  

Some key points about localStorage:
- Data is stored permanently on the client, with no expiration time.
- The storage limit is usually 5-10MB per domain.
- Data is saved across browser sessions - available after browser restart or reopen.
- API methods like setItem, getItem, removeItem and clear can be used to manipulate data.

`sessionStorage` works similarly to `localStorage` but the stored data is only available for the duration of the
browser session. The data is deleted when the tab or window is closed.  
Some key points about sessionStorage:

- Data is temporary and cleared when the browsing session ends.
- It is isolated to the current tab/window. Data is visible only to that tab.
- Opening multiple same-origin tabs will result in separate sessionStorage for each tab.
- Closing the tab/window will delete that session's sessionStorage.

---

**What is `data-` attribute good for?**  
The `data-` attribute is used to store custom data private to the page or application. Here are some common uses for it:
- Attach custom data to DOM elements, like user info or any other metadata. For example:
```html
<div data-user="john123">Hello</div>
```
- Store arbitrary data associated with the element, which can then be accessed via scripts. For example:
```html
<span id="saveBtn" data-key="1234">Save</span>
```
- Hook click or other events to DOM elements easily. For example:
```html
<button data-modal-target="#modal">Open Modal</button>
```
- Build custom attributes for custom components in frameworks like React, Vue etc.
- Non-visible metadata that devices can access like photos or phone numbers in online profiles.
- Attach identifying or semantic information to aid styling. For example custom color themes.
- Aid in DOM selection using attribute selectors like `$('[data-id=123]')`

---

**Explain the differences between cookies, session and local storage**  
Here are the key differences between cookies, session storage and local storage:
- **Cookies**:
  - Stored on the client
  - Sent back to server with every HTTP request
  - Size limit of 4KB
  - Expires based on lifetime options like Expires or Max-Age
- **Session Storage**:
  - Stored on the client, only available for current page session
  - Not sent to server with HTTP requests
  - Storage limit of 5-10MB
  - Cleared when session ends (tab/window closed)
- **Local Storage**:
  - Stored on the client permanently
  - Not sent to server with HTTP requests
  - Storage limit of 5-10MB
  - Persists data after session ends - never cleared by browser

---

**What are some differences that `xhtml` has compared to `html`?**  
Here are some key differences between `XHTML` and `HTML`:
- `XHTML` is stricter and enforces well-formed `XML` syntax whereas `HTML` is more forgiving of errors.
- All tags and attributes in `XHTML` must be lowercase. `HTML` allows mix of upper and lower case.
- `XHTML` tags must be properly nested and closed. `HTML` allows some tags to be unclosed.
- `XHTML` tags that don't have a close tag must be self-closed like `<br />`. `HTML` allows `<br>`
- Attributes in `XHTML` must have values enclosed in quotes. `HTML` allows unquoted values.
- ID and class attribute names in `XHTML` must start with a letter. `HTML` allows starting with number.

---

**What are web workers?**  
Web workers provide a way to run JavaScript code in a background thread separate from the main execution thread of a
web application. Web workers allow long-running scripts to work in the background so that they do not block the UI,
thereby improving performance and responsiveness. The UI and workers run on separate threads and communicate via events.

---

**What is the purpose of cache busting and how can you achieve it?**  
Cache busting is a technique used to force browsers to load a new fresh copy of a resource instead of serving from its
cache. This is useful when you update CSS, JavaScript or image files but the browser keeps using the old cached copy.
Some common ways to achieve cache busting:
- Append a query string to the URL with a version number or timestamp. For example, `style.css?v=1.2`
- Include a file version in the filename like ``style.1.2.css` and update it on each change.
- Configure server response headers to prevent caching for a resource. For example `Cache-Control: no-cache, no-store`.
- Change the file path of the resource while keeping the name same. For example, at v1 use `/css/style.css` and at v2 use `/css/v2/style.css`.
- Use file hashing to generate unique filenames like `style.f23ffacd.css` that change when file content changes.
- Use versioning inside asset URLs referenced from HTML/CSS files. For example `<script src="/js/script.1.2.js">`

---

**Discuss the differences between an html specification and a browser's implementation thereof.**  
There are a few key differences between an HTML specification and a browser's implementation of that specification:
- Specifications are created by standards bodies like the W3C to define HTML and web technologies. Browsers then implement these specifications in their own engines.
- Specifications describe ideal or recommended behavior. But browsers may interpret or implement parts of a spec differently.
- Browser implementations often lag behind the latest specifications. New specs take time to be fully supported.
- Browsers may only partially implement a spec, ignoring certain optional features or implementing parts of a spec they need.
- Specs are ongoing with new additions and changes. Browsers have to constantly update their engine to keep up with specs.

---

**Describe the differences between cookie, sessionStorage and localStorage**  
Here are the main differences between cookies, sessionStorage and localStorage:
- **Cookies:**
  - Stored on client-side
  - Automatically sent to server with HTTP requests
  - Small size, around 4KB
  - Can set expiration time
  - Accessible from both client and server-side
- **sessionStorage:**
  - Stored on client-side only
  - Not sent to server automatically
  - Around 5-10MB storage
  - Persists only until browser tab is closed
  - Accessible only from client-side
- **localStorage:**
  - Stored on client-side only
  - Not sent to server automatically
  - Around 5-10MB storage
  - Persists until explicitly cleared
  - Accessible only from client-side

---

**What does the DOCTYPE do?**  
The DOCTYPE declaration serves a few important purposes in HTML pages:
- It tells the browser which version of HTML is being used on the page. This helps the browser render the page correctly.
- It triggers standards mode rendering in browsers. Without a DOCTYPE, browsers may fall back to quirks mode, which has unpredictable results.
- It prevents the browser from switching to quirks mode when small mistakes exist in the HTML. Only major mistakes will trigger quirks mode.
- For HTML5, it looks like this: `<!DOCTYPE html>`
- For older XHTML pages, the DOCTYPE declaration references the DTD (document type definition) which defines the rules of that version of HTML.
- It is optional in HTML5 but required in XHTML pages.
- The DOCTYPE should be at the very start of the HTML document, even before the <html> tag.
- DOCTYPE doesn't represent a tag, just a declaration. It doesn't have a closing tag.

---

**What is progressive rendering?**  
Progressive rendering refers to the technique of displaying content to the user as quickly as possible as the page
loads. It improves perceived performance and responsiveness.
Some ways progressive rendering is achieved:
- HTML is delivered first so browser can start parsing immediately.
- Critical CSS is loaded before any other assets to allow browser to start rendering pagelayout.
- JavaScript and images are loaded asynchronously without blocking HTML parsing.
- Browser events like DOMContentLoaded are used to add behavior as page becomes interactive.
- Content is strategically ordered on the server side to render most important content first.
- Skeleton screens and placeholder content gives user a quick first paint. Details are filled in later.
- Techniques like CSS animations or spinners mask any network delays in fetching assets.

So in essence, progressive rendering delivers content incrementally, prioritizes visibility of most important content
first and utilizes strategies to unblock rendering pipeline. This results in faster time-to-content and a more
responsive feel for users.

---

**Why would you use a `srcset` attribute in an image tag? Explain the process of browser uses when evaluating
the content of this attribute**  
The `srcset` attribute is used to provide multiple image sources that browsers can choose between based on viewport
size, device resolution, and other factors. Here is how browsers evaluate and use `srcset`:
1. The browser first looks at all the image candidates in srcset and their associated size descriptors like width, pixel density, etc.
2. It then looks at the current environment - viewport size, device resolution, etc. to determine which image would best suit.
3. If there is a matching image source, the browser will pick the image with appropriate size and resolution.
4. The chosen image is then loaded into the <img> element and rendered on the page.
5. If no matching source is found, the browser loads the default image specified in the src attribute.

Some benefits of using srcset:
- Allows serving smaller image files to mobile devices saving bandwidth.
- Images load faster as optimal resolution is served for the device.
- Pages load faster and smoother due to faster image loading.
- Provides better image quality and resolution across various screen sizes.

---

**What is the purpose of main element?**  
The `<main>` element in `HTML5` represents the main content area of the document. Here are some key points about the
`<main>` element:
- It defines the main content section of the page that is unique to the document.
- It encapsulates content that is directly related to the central subject of the page.
- There can only be one `<main>` element on a page as it denotes the primary content.
- It is different from `<div>` in that it has semantic meaning - indicating the central unique content.
- Using `<main>` allows assistive technologies like screen readers to identify the main content area easily.
- `<main>` should not contain content repeated across documents like headers, footers, sidebars etc.
- `<article>`, `<section>` and other content tags can be used within `<main>` to further divide the content.
- On simple pages with not much other content, `<main>` may wrap most of the page.

---

**What is an HTML preprocessor?**  
An HTML preprocessor is a tool that lets you generate HTML markup using a shorthand syntax. Some common HTML
preprocessors are:
- `Pug (formerly Jade)` - Uses indentation rather than closing tags and allows writing HTML in a shorter way.
- `Slim` - Similar to Pug, but uses simplified syntax that replaces shorthand with spacial characters like '-' and '.'
- `Handlebars` - Uses Mustache style templating in HTML for dynamic content.
- `Markdown` - Markdown syntax can be compiled to generate HTML.
- `HAML` - Intends to make HTML semantic and reusable with a simplified syntax.

---

**What are the building block of `HTML5`?**  
Here are some of the core building blocks and major features of `HTML5`:
- `Semantic Elements` - New elements like `<header>`, `<footer>`, `<article>`, `<section>` etc to provide better document structure and meaning.
- `Forms` - New form controls like calendar, date, time, email, url, search input types for better mobile form experiences. Attributes like placeholder, required, autofocus etc.
- `Multimedia` - `<video>` and `<audio>` tags for native multimedia embedding. Support for `SVG` vector images.
- `Connectivity` - Server Sent Events and WebSockets for efficient real-time communication between server and client.
- `Offline & Storage` - Application Cache and Web Storage APIs `(localStorage & sessionStorage)` for building offline-capable web apps.
- `3D Graphics` - `Canvas 2D` and `WebGL` for native 3D graphics and visualizations directly on the web.
- `Performance` - `Web workers` for multithreading processing. Template and `defer` for faster loading.
- `Device Access` - `Geolocation`, `Device Orientation Events`, `Touch Events` for tapping into device capabilities.
- `Styling` - CSS3 for flexible box layout, 2D/3D transforms, animation, shadows etc.
- `Accessibility` - New elements for better `ARIA` support.

---

**Why to use `HTML5` semantic tags?**  
Here are some key benefits of using semantic `HTML5` tags like `<header>`, `<nav>`, `<section>`, `<article>` etc:
- More meaningful structure - The semantics help describe the purpose and improve the understandability of the content.
- Better accessibility - Screen readers can identify the semantic elements to provide better page navigation and context.
- Improved SEO - Search engines give weight to headers, navigation and main content which aids rankings and discoverability.
- Easier to style - Semantic elements can be precisely targeted compared to generic `<div>` and `<span>`.
- Maintainability - The semantic structure helps organize the code better and makes changes easier in the long run.
- Interoperability - Semantics allow conveying intent that can be understood across different devices, screen readers etc.
- Smaller file size - No need for extra classes and attributes just for styling.
- Forward compatibility - New elements introduced later will have consistent meaning.

---

**How would you select svg or canvas for your site?**  
Here are some key factors to consider when choosing between SVG and Canvas in a website:
- SVG is better for vector graphics like shapes, lines, text etc that need to scale smoothly. Canvas provides more pixel-level control for bitmap graphics
- SVG elements are part of the DOM. Styles and attributes can be changed dynamically using JavaScript. Canvas content requires redrawing for any change
- SVG has better support for accessibility features like screen reader compatibility. Canvas is less accessible
- SVG files are smaller generally. Canvas images require more file size for high resolution
- SVG allows CSS animations and transitions directly on elements. Canvas requires JavaScript code to animate
- SVG can link to external CSS and JavaScript files. Canvas cannot reference external resources
- Canvas is better for graphics intensive applications like games, image processing, graphs etc
- SVG integrates with other DOM elements. Canvas is independent and just a rectangle on the page

So in summary, choose SVG for simple vector graphics and interactivity. Prefer Canvas for intensive gaming or bitmap
graphics needs. Evaluate interactivity needs, file size constraints and browser support as well.

---

**What kind of things must you be wary of when designing or developing for multilingual sites?**  
Here are some considerations when designing/developing multilingual websites:
- Be aware of the text expansion that happens in some languages and adjust layouts accordingly.
- Account for longer words and sentences that may affect things like line lengths or paragraph sizes.
- Ensure UI components and buttons have sufficient space for localized text.
- Use relative units like ems/rems instead of fixed pixels in CSS.
- Allow extra spacing in design for expansion or change in word order.
- Set the base language direction in HTML tag rather than CSS for optimum experience.
- Check for FORM field character limits as labels may expand.
- Use external JSON/XML for all UI strings and content to allow easy translation.
- Enable RTL layouts if supporting right-to-left languages like Arabic, Hebrew.
- Choose fonts that support all the languages you are targeting.
- Verify designs work across different scripts like Latin, Chinese, Arabic etc.
- Ensure site meets needs of locales like formats, culture preferences etc.

So in summary, always keep text expansion, alternate language directions and localization needs in mind right from the
initial design phase to avoid issues down the road.

---

**What is WebP?**  
WebP is an image format developed by Google that provides superior lossy and lossless compression for images on the web.
Here are some key features:
- WebP lossy images are 25-35% smaller compared to JPEG images at equivalent SSIM quality index.
- WebP lossless images are 25-35% smaller than PNG images.
- WebP supports transparency (alpha channel) at both lossy and lossless compression unlike JPEG.
- WebP supports animation just like GIFs while producing much smaller file sizes.
- WebP provides consistent image quality at all compression levels unlike JPEG.
- WebP images can use metadata for additional functionality.
- WebP is based on a subset of the VP8 video format with enhancements.
- Browser support is decent with Chrome, Opera, Edge and Android having native support.
- WebP's conversion tools allow generating WebP versions of JPEGs and PNGs.

---

**What is public key in html?**  
HTML and browsers do not have direct support for generating or working with public keys for cryptographic purposes.
Public keys are part of public key cryptography and require a complex cryptographic library to generate using algorithms
like RSA or ECC.

---

**Why is it generally good idea to position css `<link>` tags between `<head>` and javascript `<script>` tags just
before `</body>`? Do you know any exception?**  
Placing `<link>` CSS tags in the `<head>` and `<script>` JS tags just before `</body>` is generally considered a best
practice for the following reasons:

- **Benefits:**
  - CSS in <head> allows for early progressive rendering since styles are loaded before body content.
  - JS at end allows HTML and CSS to load first so page is rendered by the time scripts load.
  - Separation of structure, styling and behavior makes code easier to maintain.
  - CSS and JS stay separate from HTML structure.
  - CSS applied to all elements on page consistently.

- **Exceptions:**
  - Small inline scripts that need to execute early can remain in `<head>`.
  - Scripts that have interdependencies on each other may need to be grouped together.
  - Some CSS needs to be in `<body>` like if styles depend on JS variables.
  - Third party scripts may require being installed in `<head>` based on their requirements.

---

**What are web components?**  
Web components are a set of web platform APIs that allow you to create reusable custom elements and widgets using `HTML`,
`CSS`, and `JavaScript`.  
- **Some key capabilities of web components:**
  - `Custom Elements` - Define new HTML tags to extend the semantics of HTML.
  - `Shadow DOM` - Encapsulate styles and markup within a component.
  - `HTML Templates` - Define reusable markup templates that can be instantiated multiple times.
  - `HTML Imports` - Allow including and reusing HTML documents in other web pages.

- **Benefits of web components:**
  - `Reusable` - Can wrap functionality into modular components that can be shared.
  - `Interoperable` - Leverage web standards so components work across frameworks.
  - `Isolated` - Shadow DOM provides style and markup encapsulation.
  - `Composable` - Can define more complex components by composing other components.
  - `Platform native` - Built on underlying browser technologies rather than frameworks.
  - `Backwards compatible` - Work across modern browsers with polyfills.

---

**What is IndexedDB?**  
`IndexedDB` is a browser API that allows client-side storage and retrieval of significant amounts of structured data.
It is a `NoSQL` database that runs in the browser.  

- **Some key features of `IndexedDB`:**
  - It stores data in object stores which are like tables in traditional databases.
  - Each object store can be queried via indexes which allow fast lookups.
  - All data is stored on the client-side, no server interaction needed.
  - The API uses JavaScript promises for async operations.
  - Storage limits are significantly higher than localStorage or sessionStorage.
  - Supported by modern browsers including Chrome, Firefox, Edge.
  - Data is persisted unless explicitly deleted.
  - Useful for offline capabilities and performance.

---

**What is accessibility and ARIA role means in a web app?**  
Accessibility refers to designing web content and apps, so they can be effectively used by people with disabilities.
ARIA roles help improve accessibility.  

Some ways ARIA roles enhance accessibility:

- Roles convey semantic meaning to assistive technologies like screen readers. For example, `role="navigation"` identifies a page section as a navigation pane.
- Roles allow adding semantics where HTML elements don't fit the content. For example, `role="tabpanel"` denotes a tab panel container.
- States and properties can provide extra info like invalid form fields or live region updates.
- ARIA labels provide text alternatives where visible text is insufficient.
- ARIA can make dynamic content changes accessible via live regions which are announced by screen readers.
- ARIA `valuenow/valuemin/valuemax` provide progress indicator state.
- Keyboard navigation and focus management rely on proper ARIA usage.

---
