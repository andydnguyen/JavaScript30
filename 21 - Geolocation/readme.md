# Project 21 - Geolocation

## Demo

https://andycodes.io/JavaScript30/21%20-%20Geolocation

## Objective

For this project, I build a compass that uses the browser geolocation.

## JavaScript

To access the browser's geolocation, I used `navigator.geolocation.watchPosition()`.

To access the speed, I used `Geoposition.coords.speed`.

To rotate the compass, I use CSS Transform:

```
arrow.style.transform = `rotate(${data.coords.heading}deg)`
```
