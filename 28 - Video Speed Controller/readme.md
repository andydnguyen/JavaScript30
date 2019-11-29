# Project 28 - Video Speed Controller

## Demo

https://andycodes.io/JavaScript30/28%20-%20Video%20Speed%20Controller/

## Objective

For this project, I built a playback rate changer. Instead of a hortizonal bar, I made it a vertical bar.

## JavaScript

To calculate the height of the the bar I used:

```
  const y = e.pageY - this.offsetTop;
  const percent = y / this.offsetHeight;
```

To set the bar and the text I used:

```
  bar.style.height = height;
  bar.textContent = playbackRate.toFixed(2) + 'x';
```

To set the video playback rate, I used:

```
  video.playbackRate = playbackRate;
```
