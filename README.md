# Introduction to the DOM

## Learning Goals

* Identify the Document Object Model (DOM)
* Explain how the DOM is created
* Identify the DOM as accessed by JavaScript objects
* Introduce the Console and Chrome DevTools
* Learn how to open HTML files in the browser

## Introduction

We have learned how to write HTML and style it with CSS. We have also built our
JavaScript programming skills. With this knowledge, we're now ready to learn
**Document_Object Model (DOM) programming**.

DOM programming consists of using JavaScript to:

1. Ask the DOM to find or select an HTML element or elements in the rendered page
2. Remove and/or insert one or more elements
3. Adjust a property of selected element(s)

In other words, we can use DOM programming to create and modify content that
users see in their browsers and add interactivity to our web pages.

## Identify the Document Object Model

Let's start with a biology metaphor. Your DNA represents a code-based version of
_you_. The DOM represents a code-based version of _a web page_. If something
edits your DNA, changes will be made in your body (perhaps giving you mutant
powers). Similarly, when you change something in the DOM, you change what's
displayed in the browser.

But what exactly ***is*** the DOM? You can think of it as a "middle layer"
between the user and the underlying HTML, CSS, and JavaScript that makes up the
page. What the user is actually seeing on the page is the DOM. When the page
initially loads, the DOM represents the underlying HTML, CSS and JavaScript.
When we use JavaScript and DOM programming to modify the DOM and change what the
user sees, the underlying code is not modified: if we refresh the page, it goes
back to its original state.

### Explain How the DOM Is Created

The DOM is created when the page loads from the HTML/CSS/JavaScript that the web
server provides to the browser. Let's examine this process step-by-step:

> **NOTE**: To ensure that instructions and screenshots match up with your experience, be sure to use the [Google Chrome][chrome] browser.

1. In Google Chrome, open a tab and navigate to the [Wikipedia page for Ada Lovelace][wikipedia].
2. To see the HTML of this page, add `view-source:` to the front of the URL in
   the URL bar. Using the `view-source` URL prefix will display all the page's
   source HTML. It will look something like this:
![html-source](https://curriculum-content.s3.amazonaws.com/phase-0/intro-to-the-dom/html-source.png)
3. The browser reads this HTML, along with CSS and JavaScript defined in
   `<script>` or `<link>` tags, to create the DOM inside the browser. At this
   point, nothing is displayed on the screen. This time when nothing is
   displayed is very brief so our human eyes never really catch it.
4. The browser then uses the DOM object to create the rendered page. While we
   often learn that browsers "display HTML," that's not exactly accurate.
   Browsers use the HTML to create a "middleman" that they, in turn, use to
   display the structured and styled content.

### Identify the DOM as Accessed by JavaScript Objects

We can access the DOM, using JavaScript and DOM programming, through two
_variables_: `window` and `document`.

The `window` variable points to an _object_ that represents Chrome's information
about the browser, well, "window." It has many functions, but the main one is
"it's a place where everything is." Not to be Zen here, but a browser without a
`window` is like the universe before the Big Bang; there's just... _nothing_.

Like all objects, the `window` has properties and methods. For example, we can
access operating system browser information like:

```javascript
window.innerHeight;
// returns the inner height of the browser window.
```

For the most part, we won't interact with `window`: we don't want to mess with
the container of everything or with operating system stuff. We want, rather, to
change content. To do that, we'll focus on an object called `document`.

As an _object_, `document` has _properties_:

```javascript
document.URL; //=> https://en.wikipedia.org/wiki/Ada_Lovelace
```

As an _object_, `document` also has _methods_:

```javascript
document.querySelector("h1"); //=> Returns the element on the page with an id attribute equal to "firstHeading" 
```

The _methods_ and _properties_ that the DOM provides via its objects is called
the DOM's "Application Programming Interface," or "API." It's just a programming
word that you're likely to see online. But it just means "the things that these
objects know how to do."

## The Browser Console and Chrome Developer Tools

Every major browser comes with a built-in set of developer tools that you can
use to inspect, modify, and debug the content of a web page. To [open the dev
tools in Chrome][open-tools], press `Ctrl+Shift+J` (Windows / Linux) or
`Cmd+Opt+J` (Mac). Chrome ships with a whole suite of useful developer tools,
but the only one we care about for now is the JavaScript console.

The console is an environment in the browser where we can type and run
JavaScript code in the context of the current browser window. The console is
_sandboxed_, meaning the only resources it has access to are those loaded on the
current page. Once we start declaring variables and functions in separate
JavaScript files, we'll be able to access and play around with them in the
console. The console is the single best tool for debugging JavaScript in the
browser, so start familiarizing yourself with it now.

The `Ctrl+Shift+J` / `Cmd+Opt+J` command should open up straight into the
console. If for whatever reason, it doesn't, you can always click on `Console`
in the dropdown (when the DevTools are collapsed) or in the list of tabs:

<picture>
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/opening_the_console.webp" type="image/webp">
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/opening_the_console.gif" type="image/gif">
  <img src="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/opening_the_console.gif" alt="Opening the console">
</picture>

If at any point the console becomes cluttered with errors, warnings, or anything
else, click the `Clear console` button:

<picture>
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/clearing_the_console.webp" type="image/webp">
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/clearing_the_console.gif" type="image/gif">
  <img src="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/clearing_the_console.gif" alt="Clearing the console">
</picture>

Okay, okay, enough background and setup. Let's write some code!

### Coding in the Console

You can write and test out JavaScript code in the console. We'll start off with
some simple math. In the console, type `1 + 1` and press enter. You should see
the number `2` appear.

<picture>
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/math_in_console.webp" type="image/webp">
  <source srcset="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/math_in_console.gif" type="image/gif">
  <img src="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/math_in_console.gif" alt="Math in the console">
</picture>

Try out some other mathematical expressions and see what they return.

Next up, let's write some text. To make sure the JavaScript engine knows that we're trying to write some literal text, we need to wrap it in quotation marks, like so:

```js
"This is some literal text in JavaScript!"
```

Go ahead and type that classic phrase, `"Hello, world!"`, into the console and
press enter. It returned `"Hello, world!"` right back to us. Try typing some
more literal text into the console, such as your name. Don't forget the
quotation marks!

<img src="https://curriculum-content.s3.amazonaws.com/web-development/js/basics/intro-to-javascript/text_in_console_300.gif" alt="Text in the console">

We can go far beyond simple literal expressions: we can create variables, loops,
or if statements in the console. We can even define and run functions!

> **Note:** It's impossible to overstate how important practice is when you're learning a new programming language. As you continue moving through the JavaScript curriculum, you should almost always have a browser console open. Code along with every example. Get used to the syntax and familiarize yourself with the errors that arise when you mistype something. Clear the console or simply refresh the page whenever you need a clean slate. Code, code, code, **code**, ***code***.

## Opening Files in the Browser

In this section, you will begin working with HTML files (most often,
`index.html`). In order to view the results of the coding you'll be doing,
you'll need to open the file in the browser. Instructions for each programming
environment are as follows:

* **Local environment on Mac**: Run `open index.html` in the terminal.
* **Local environment using WSL/Ubuntu**: Run `explorer.exe index.html` in the
  terminal.
* **AWS IDE**: right-click on the `index.html` file in the file tree and select
  "Preview." There will be a button in the upper right corner that will "pop"
  the page into a new tab in the browser.

Keep these instructions handy &mdash; you will be doing this often.

> **Note:** In order for these instructions to work, you will need to have Google Chrome set as your default browser. You can find [instructions for Mac and Windows here][default-browser].

## Conclusion

In this lesson we learned about the DOM, which is a "middle layer" that presents
the HTML, CSS and JavaScript loaded by the browser when we visit a page. We
normally interact with it through the `document` object. Because it is the
"source of truth" for what browsers display, changes to the DOM create changes
in the browser screen. We also learned how to access the Chrome Developer Tools
and use the Console to try out code as we're building our programs.

## Resources

* [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
* [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

[chrome]: https://www.google.com/chrome/browser/desktop/index.html
[wikipedia]: https://en.wikipedia.org/wiki/Ada_Lovelace
[open-tools]: https://developers.google.com/web/tools/chrome-devtools/console/#open_as_panel
[default-browser]: https://support.google.com/chrome/answer/95417?hl=en&co=GENIE.Platform=Desktop
