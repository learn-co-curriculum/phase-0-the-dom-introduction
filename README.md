# Introduction to the DOM

## Learning Goals

1. Identify the Document Object Model (DOM)
2. Explain how the DOM is created
3. Identify the DOM as accessed by JavaScript objects

## Introduction

Previously we've learned that JavaScript was born in the browser along with
the Document Object Model (DOM). We've acquired some JavaScript sight words,
let's balance things out by learning about the DOM.

### Identify the Document Object Model

Let's start with a biology metaphor. Your DNA represents a code-based version of
you. The DOM represents a code-based version of a web page. If something edits
your DNA, <span style="text-decoration: line-through">mutant powers</span>
changes will be made in your body. Similarly, if something changes the DOM,
what's displayed in the browser _changes as well_.

### Explain How the DOM Is Created

The DOM is created when the page loads from the HTML that the web server
provides the browser. Let's step through that process.

> **NOTE**: We use [Google Chrome][chrome].

### Change the URL of a Web Page to View the Source

1. In a Google Chrome browser, copy the current URL and open it in another tab.

2. To see the HTML of this page, add `view-source:` to the front of the URL in
the new tab. By using the `view-source` URL prefix, all the page's source HTML
appears. It will look something like this:

   ![html-source](https://s3.amazonaws.com/learn-verified/html-javascript-lesson.png)

3. The browser reads this HTML, along with CSS and JavaScript defined in
   `<script>` or `<link>` tags, to create the DOM inside the browser. At this
   point, nothing is displayed on the screen. This time when nothing is
   displayed is very brief so our human eyes never really catch it.

4. The browser then uses the DOM object to create the rendered page. While we
   often learn that browsers "display HTML" that's not exactly accurate.
   Browsers use the HTML to create a "middleman" that they, in turn use to
   display the structured and styled content.

### Identify the DOM as Accessed by JavaScript Objects

Recall that JavaScript is object-oriented. The DOM is available inside Chrome
through two _variables_: `window` and `document`.

The `window` variable points to an _object_ the represents Chrome's information
about the browser, well, "window." It has many functions, but the main one is
"it's a place where everything is." Not to be Zen here, but a browser without
`window` is like the Universe before the Big Bang: there's just..._nothing_
everywhere where it wasn't. It's in the `window` that the Things are defined
(`Array` and `Number`).

In the `window`, JavaScript also tracks operating system browser information
like:

```javascript
window.innerHeight;
// returns the inner height of the browser window.
```

Like all objects, `window` also has _methods_.  We won't use them too much.
We don't want to mess with the container of everything that is or operating
system stuff.

We want, rather, to change content. We're going to focus on an object called
`document`.

As an _object_, `document` has _properties_:

```javascript
document.URL //=> http://www.flatironschool.com
```

As an _object_ `document` also has _methods_:

```javascript
document.write("Moof") //=> Removes all existing DOM content, replaces it with "Moof"
```

The _methods_ and _properties_ that the DOM provides via its objects is called
the DOM's "Application Programming Interface", or "API." It's just a programming
word that you're likely to see online. But it just means "the things that these
objects know how to do."


## Conclusion

In this lesson we met our partner, the DOM, a JavaScript object that is a
representation of the HTML, CSS and JavaScript loaded by the browser when we
visit a page. We normally interact with it through the `document` object.
Because it is the "source of truth" for what browsers display, changes to the
DOM create changes in the browser screen.

## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

[chrome]: https://www.google.com/chrome/browser/desktop/index.html

<p class='util--hide'>View <a href='https://learn.co/lessons/fewpjs-introduction-to-the-dom-to-get-started'>Introduction to the DOM</a> on Learn.co and start learning to code for free.</p>
