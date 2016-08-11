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
    2. [Meta Tag](#meta-tag)
    3. [General HTML Markup](#general-html-markup)
    4. [Performance](#perfomance)
    5. [HTML Comments](#html-comments)
5. [CSS Markup](#css-markup)
    1. [General CSS Principles](#general-css-principles)
    2. [Naming Convention](#naming-convention)
    3. [CSS Comments](#css-comments)
6. [JavaScript](#javascript)
    1. [General JS Principles](#general-js-principles)
    2. [Debuging](#debuging)
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
<meta charset=utf-8>
```

### Meta Tag

### General HTML Markup

### Performance

### General CSS Principles

### Naming Convention

### CSS Comments

### General JS Principles

### Debuging

### JS Comments

### Using Git

### Readme File

### External Tools