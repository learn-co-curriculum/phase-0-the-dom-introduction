# Introduction to the DOM

## Learning Goals

1. Identify the Document Object Model (DOM)
2. Explain How the DOM is Created
3. Identify the DOM as accessed by JavaScript objects

## Introduction
Previously we've learned that JavaScript was born in the browser along with
the Document Object Model (DOM). We've acquired some JavaScript sight words,
let's balance things out by learning about the DOM.


## Identify the Document Object Model

Let's start with a biology metaphor. Your DNA represents a code-based version
of you. The DOM represents a code-based version of a web page. If something
edits your DNA, <span style="text-decoration: line-through">mutant powers</span> changes will be made in your body. Similarly,
if something changes the DOM, what's displayed in the browser changes as
well.

## Explain how the DOM is created

The DOM is created when the page loads from the HTML that the web server
provides the browser. Let's step through that process.

> **NOTE**: We use [Google Chrome][chrome].


### Change the URL of a web page to view the source

1. In a Google Chrome browser, copy the current URL and open it in another tab.
2. To see the HTML of this page, add `view-source:` to the front of the URL in the
new tab. By using the `view-source` URL prefix, all the page's source HTML
appears. It will look something like this:
   ![html-source](https://s3.amazonaws.com/learn-verified/html-javascript-lesson.png)
3. The browser reads this HTML, along with CSS and JavaScript defined in
   `<script>` or `<link>` tags, to create the DOM inside the browser. At this
   point, nothing is displayed on the screen. This time when nothing is
   displayed is very brief so our human eyes never really catch it.
4. The browser then uses the DOM object to create the rendered page. While we
   often learn that browsers "display HTML", that's not exactly accurate.
   Browsers use the HTML to create the DOM that they use to
   display the structured and styled content.

## Identify the DOM as accessed By JavaScript objects

Recall that JavaScript is Object-Oriented. The DOM is available inside Chrome
through two variables: `window` and `document`.

The `window` variable points to an `object` that represents Chrome's information
about the browser window. It has many functions, but the main one is "it's a
place where everything is." Before JavaScript and `window`, a browser was like
the Universe before the Big Bang. It's in the `window` that the Things are
defined (`Array` and `Number`).

In the `window`, JavaScript also tracks operating system browser information
like:

```javascript
window.innerHeight;
// returns the inner height of the browser window.
```

Like all objects, `window` also has methods.  We won't use them too much. We
don't want to mess with the container of everything or operating system stuff.

We want, rather, to change content. We're going to focus on an object called
`document`.

As an `object`, `document` has properties:

```javascript
document.URL //=> http://www.flatironschool.com
```

As an `object`, `document` also has `methods`:

```javascript
document.write("Moof") //=> Removes all existing DOM content, replaces it with "Moof"
```

The `methods` and properties that the DOM provides via its objects is called
the DOM's "Application Programming Interface", or "API." It's just a programming
word that you're likely to see online. But it just means "the things that these
objects know how to do."


## Conclusion

In this lesson we've met the DOM, a JavaScript object that is a
representation of the HTML, CSS and JavaScript loaded by the browser when we
visit a page. We normally interact with it through the `document` object.
Because it is the "source of truth" for what browsers display, changes to the
DOM create changes in the browser screen.


## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

[chrome]: https://www.google.com/chrome/browser/desktop/index.html