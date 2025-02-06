# Uncommon HTML Bug: JavaScript DOM Access Before Load

This repository demonstrates a common yet subtle error in HTML: attempting to access a DOM element using JavaScript before the element exists in the DOM tree.  This typically happens when JavaScript code is placed in the `<head>` section of an HTML document, which executes before the browser finishes parsing the `<body>` section where the target element might reside.

## The Bug

The `bug.html` file contains a simple HTML page with a div element. A JavaScript function attempts to modify the inner HTML of this div element, but the function is called *before* the div element is fully loaded, causing an error.

## The Solution

The `bugSolution.html` file shows the correct way to handle this situation. By either placing the JavaScript code at the end of the body or using an event listener (`DOMContentLoaded`), we ensure that the JavaScript code executes only after the DOM is fully ready.
