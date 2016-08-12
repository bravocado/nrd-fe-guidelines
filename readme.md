# Narrada Front-end Guidelines

### Description
This document contains the guidelines and best practices for the front-end web development team at [Narrada Communications](http://narrada.com). Each item here represents either:

1. A reminder to follow existing standards or industry conventions.
2. Guidance on what constitutes professional patterns and organization.
3. A decision we've made favoring one method over its alternatives.

What this document is not is a series of explanations as to how front-end technologies work; a basic familiarity is assumed. It also does not provide evaluations of the pros and cons of various alternatives unless there is common confusion about which option is best.

These guidelines have been compiled looking at various previously written guidelines in some sections been directly quoted.


### Goals
Our motivations in creating this document are to:

1. Foster code consistency across our projects.
2. Facilitate ease of maintenance.
3. Ensure we create professional quality web sites.
4. Guide staff on-boarding or educate new developers.

This document is not intended to replace common sense, conventions requested by particular clients, teams, or prevent expressive or creative solutions to problems. Team or project-specific agreements or client requests will always supersede this document's content.


### Contributing
To contribute to this project please follow this step:
- clone this repo on draft branch. `git clone -b draft https://github.com/bravocado/nrd-fe-guidelines`
- create your own branch with the feature that you want to add `user/some-feature`
- submit your pull request to draft branch

---

## Contents
1. [General Guidelines](#general-guidelines)
    1. [Indentation](#indentation)
    2. [Readability and Compression](#readability-and-compression)
2. [Browser Support](#browser-support)
3. [Base Frameworks](#base-frameworks)
4. [HTML Markup](#html-markup)
    1. [Document Type](#document-type)
    2. [Open Graph](#open-graph)
    3. [General HTML Markup](#general-html-markup)
    4. [Performance](#perfomance)
    5. [HTML Comments](#html-comments)
5. [CSS Markup](#css-markup)
    1. [General CSS Principles](#general-css-principles)
    2. [Naming Convention](#naming-convention)
    3. [CSS Comments](#css-comments)
6. [JavaScript](#javascript)
    1. [General JS Principles](#general-js-principles)
    2. [JS Structure](#js-structure)
    3. [Debuging](#debuging)
    3. [JS Comments](#js-comments)
7. [Code Distribution](#code-distribution)
    1. [Using Git](#using-git)
    2. [Readme File](#readme-file)
8. [External Tools](#external-tools)

---

## General Guidelines

1. All front-end code should display clear separation of presentation, content, and behaviour.
2. Markup should be well formed, semantically correct and generally valid.
3. Gracefully degrade functionality when not present (e.g GPS, box-shadow, forms etc).

### Indentation
For all languages, indent your code with spaces. The default tab size should be set as 4.

### Readability and Compression
We encourage readability over file-size when it comes to maintaining existing files. Plenty of white-space is encouraged, along with ASCII art, where appropriate. There is no need for any developer to purposefully compress HTML or CSS, nor obfuscate JavaScript.
We should use server-side or build processes to automatically minify and gzip all static client-side files, such as CSS and JavaScript.

## Browser Support
- IE9+
- Google Chrome 29+
- Firefox 47+
- Safari 9.1+
- Opera 39+
- Android Browser 4.4+
- Chrome for Android 51+

## Base Frameworks
We encourage you using [Bootstrap](getbootstrap.com). Since we have tight deadlines, we need a fast and robust front-end frameworks and also have a big community in case you need a hint when debugging.

### Document Type
Keep your code terse. Forget about your old XHTML habits.

```html
<!doctype html>
```

All markup should be delivered as UTF-8, as it's the most friendly for internationalization. It should be designated in both the HTTP header and the head of the document.

```html
<meta charset=utf-8>
```

### Open Graph
The Open Graph protocol enables any web page to become a rich object in a social graph. For instance, this is used on Facebook to allow any web page to have the same functionality as any other object on Facebook.
To turn your web pages into graph objects, you need to add basic metadata to your page. We've based the initial version of the protocol on RDFa which means that you'll place additional `<meta>` tags in the `<head>` of your web page. The four required properties for every page are:

- og:title - The title of your object as it should appear within the graph, e.g., "The Rock".
- og:type - The type of your object, e.g., "video.movie". Depending on the type you specify, other properties may also be required.
- og:image - An image URL which should represent your object within the graph.
- og:url - The canonical URL of your object that will be used as its permanent ID in the graph, e.g., "http://www.imdb.com/title/tt0117500/".

Twitter has its own `<meta>` tags that are similar to the Open Graph protocol, but uses the "twitter" prefix instead of "og". As with Facebook, only a few are required. The type of display format we're requesting from Twitter is also specified:

```html
<meta name="twitter:title" content="your title goes here">
<meta name="twitter:description" content="your description here">
<meta name="twitter:image" content=" http://url.com/image.jpg">
<meta name="twitter:card" content="summary_large_image">
```


### General HTML Markup
The following are general guidelines for structuring your HTML markup. Authors are reminded to always use markup which represents the semantics of the content in the document being created.

- Use `<p>` elements for paragraph delimiters as opposed to multiple `<br />` tags.
- Items in list form should always be housed in a `<ul>`, `<ol>`, or `<dl>`, never a set of `<div>`s or `<p>`s.
- Make use of `<thead>`, `<tbody>`, and `<th>` tags (and Scope attribute) when appropriate.
- Make use of `<dl>` (definition lists) and `<blockquote>`, when appropriate.
- Use `<label>` fields to label each form field. The `for` attribute should associate itself with the input field, so users can click the labels and obtain focus.
- Tables shouldn't ever be used for page layout – only for tabular data.

While the HTML5 specification defines quotes around attributes as optional for consistency with attributes that accept whitespace, all attributes should be quoted.

```html
<a href="mylink.html" title="My Link Title" data-attribute="32">This is my Link</a>
```

### Performance
Unless there's a valid reason for loading your scripts before your content, don't block the rendering of your page. If your style sheet is heavy, isolate the styles that are absolutely required initially and defer the loading of the secondary declarations in a separate style sheet. Two HTTP requests is significantly slower than one, but the perception of speed is the most important factor.

```html
<!doctype html>
<meta charset="utf-8">
<title>Hello, world.</title>
<body>
    <p>...</p>
</body>
<script src="your-script.js"></script>
```

### General CSS Principles

- Every time you write inline styles in your markup, a front-end developer somewhere dies - whether it's in a style tag or directly in the markup. Don't do it.
- Add CSS through external files, minimizing the number of files, if possible. CSS should always be included in the `<head>` of the document.
- Use the `<link>` tag to include, never `@import`.
- All CSS rules should have a space after the selector colon and a trailing semi-colon.
- Don't over qualify class or ID selectors. Leads to specificity issues further down the line.
- ID's are an unique identifier. Each element can have only one ID. Each page can have only one element with that ID.
- Classes are **NOT** unique. Any styling information that needs to be applied to multiple objects on a page should be done with a class.
- For each level of markup nesting, indent your CSS to match. For example:

```css
nav {}
    nav li {}
        nav li a {}

.content {}
    .content p {}
```

### Naming Convention


### CSS Comments
We encourage liberal use of whitespace, comments, and descriptive variable names as appropriate for writing easy-to-read code. You will use automated server-side or other build processes to optimize files (eg: Gulp, Grunt or CodeKit). The ability for another developer to read the code is paramount above other concerns, especially if optimization can be handled another way.

Use block and describe your stylesheet

```css
/**
 *
 * Block comment
 *
 */
```

Use section comment for each section

```css
/*=============================================
=            Section comment block            =
=============================================*/

...

/*=====  End of Section comment block  ======*/
```

Use sub-section to identify a small part of your stylesheet

```css
/*----------  Subsection comment block  ----------*/
```

### General JS Principles

- Use external JavaScript files. **Do NOT include JavaScript in-line in the page unless there is a good reason**.
- Name variables and functions logically and in camelCase. Sensible names that are long are preferred to short names that make no sense.
- Try to write functions to follow the principle that they should do one thing and do it well. If you can see that a function is becoming more complex, abstract it out into multiple functions - it will become more readable, reusable and will make more sense to someone unfamiliar to the code.
- Prefix jQuery collection variables with the dollar ($) character e.g `$headerChildren`
- Class declarations should start with a capital letter.
- Constants or configuration variables should be at the start of a class and written in CAPS.

### JS Structure
When you're using jQuery as your plugin, please follow this structure:

```javascript
// good
$(function(){
    func(1);
    func(2);
});

// bad
$(function(){
    func(1);
});
$(function(){
    func(2);
});

```

### Debuging

### JS Comments

### Using Git

### Readme File

### External Tools