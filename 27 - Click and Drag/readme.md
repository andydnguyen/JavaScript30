# Project 27 - Click and Drag

## Demo

https://andycodes.io/JavaScript30/27%20-%20Click%20and%20Drag/

## Objective

For this project, I built a click and drag to scroll.

## JavaScript

When we clicked on the screen (`mousedown`), we want to record two points:

```
  startX = e.pageX - slider.offsetLeft;
  scrollLeft = slider.scrollLeft;
```

When we move the mouse (`mousemouse`), we want to record two points and reassign the `slider.scrollLeft`:

```
  const x = e.pageX - slider.offsetLeft;
  const walk = (x - startX) * 3;
  slider.scrollLeft = scrollLeft - walk;
```
