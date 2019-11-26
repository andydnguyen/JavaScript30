# Project 25 - Event Capture, Propagation, Bubbling and Once

## Demo

https://andycodes.io/JavaScript30/25%20-%20Event%20Capture,%20Propagation,%20Bubbling%20and%20Once/

## Objective

For this project, I learned about Event Capture, Propagation, Bubbling and Once

### Bubbling

Event Bubbling is the event starts from the deepest element or target element to its parents, then all its ancestors which are on the way to bottom to top. At present, all the modern browsers have event bubbling as the default way of event flow.

### Event Capture

Event Capturing is the event starts from top element to target element. Modern browser doesn’t support event capturing by default but we can achieve that by code in JavaScript.

### AddEventListener capture

AddEventListener has an option called `capture`. `capture`: A Boolean indicating that events of this type will be dispatched to the registered listener before being dispatched to any EventTarget beneath it in the DOM tree.

`div.addEventListener('click', logText, { capture: true })`

### AddEventListener once

AddEventListener has an option called `once`. `once`: A Boolean indicating that the listener should be invoked at most once after being added. If true, the listener would be automatically removed when invoked.

### e.stopPropagation();

`e.stopPropagation();` tells it to stop bubbling
