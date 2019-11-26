# Project 24 - Sticky Nav

## Demo

https://andycodes.io/JavaScript30/24%20-%20Sticky%20Nav/

## Objective

For this project, I built a navigation bar to stick when it reaches the top of the screen.

## JavaScript

In order to get the nav bar to stick, you have to first know where the top of the nav bar is to the page:

```
const nav = document.querySelector('#main');
const topOfNav = nav.offsetTop;
```

To determine when to make the nav bar stick, check to see if `window.scrollY` is greater than or equal to `nav.offsetTop`. If it is, we want to add the class `fixed-nav` with `document.body.classList.add('fixed-nav');`

The class `fixed-nav` will set the postion to `fixed`.

### Issue with Jumping Screen

The issue with the jump is because when we set the position to `fixed`, the nav does not take any space and it moves everything else up. To fix this, we have to offset it by setting the padding top to equal the height of the nav bar with `document.body.style.paddingTop = nav.offsetHeight + 'px';`
