# Project 22 - Follow Along Link Highlighter

## Demo

https://andycodes.io/JavaScript30/22%20-%20Follow%20Along%20Link%20Highlighter/

## Objective

For this project, I built instyle css using JavaScript that would follow along the links based on `mouseenter`.

## JavaScript

The main concept of this project was `this.getBoundingClientRect()` which returns the size of an element and its position relative to the viewport.

When setting the top and left position, you have to include the `window.scrollY` and `window.scrollX` due to the position when scrolling.

### Instyle CSS

```
highlight.style.width = `${coords.width}px`;
highlight.style.height = `${coords.height}px`;
highlight.style.transform = `translate(${coords.left}px, ${coords.top}px)`;
```
