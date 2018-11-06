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

- Identify the DOM

## Explain How the DOM is Created

The DOM is created when the page loads from the HTML that the web server
provides the browser. Let's step through that process.

> **NOTE**: We use [Google Chrome][chrome].

### Change the URL of a web page to view the source

1. In a Google Chrome browser, copy the current URL and open it in another tab
2. To see the HTML of this page, add `view-source:` to the front of the URL in the new tab
   By using the `view-source` URL prefix, all the page's source HTML appears.
   It will look something like this:
   ![html-source](https://s3.amazonaws.com/learn-verified/html-javascript-lesson.png)
3. The browser reads this HTML, along with CSS and JavaScript defined in
   `<script>` or `<link>` tags, to create the DOM inside the browser. At this
   point, nothing is displayed on the screen. This time when nothing is
   displayed is very brief so our human eyes never really catch it
4. The browser then uses the DOM object to create the rendered page. While we
   often learn that browsers "display HTML" that's not exactly accurate.
   Browsers use the HTML to create a "middleman" that they, in turn use to
   display the structured and styled content



## Identify the DOM as Accessed By JavaScript objects
 - JavaScript is Object-Oriented
 - the Dom is available via `window` and `document`
 - Things are defined within the `window`
 - operating system browser information is also tracked within the window
 - you can call methods on `window`, but they are not used too often as we don't want to mess with the container of everything
 - instead, we operate on `document`, which also has properties and methods
 - These properties and methods that the DOM provides via it's objects are called the DOM's "Application Programming Interface", or API


## Conclusion

In this lesson we've met our partner, the DOM, a JavaScript object that is a
representation of the HTML, CSS and JavaScript loaded by the browser when we
visit a page. We normally interact with it through the `document` object.
Because it is the "source of truth" for what browsers display, changes to the
DOM create changes in the browser screen.


## Resources

- [CSS Tricks - What is the DOM?](https://css-tricks.com/dom/)
- [MDN - The DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

[chrome]: https://www.google.com/chrome/browser/desktop/index.html