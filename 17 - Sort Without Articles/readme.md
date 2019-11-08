# Project 17 - Sort Without Articles

## Demo

https://andycodes.io/JavaScript30/17%20-%20Sort%20Without%20Articles

## Objective

For projet 17, I learned how to sort band names but ignored articles likes 'an', 'the', 'a'. I used 4 different function `.replace()` `.sort()` `.map()` and `.join()`.

### .replace()

I used `.replace()` with regular expression to create a function that replace the articles with a space.

```
function strip(bandName) {
  return bandName.replace(/^(a |the |an )/i, ' ');
}
```

### .sort()

I used `.sort()` to sort the band names. You can understand `.sort()` by thinking about you're given two apples and say which one is bigger and you keep doing that over and over again until your list is sorted.

```
const sortedBands = bands.sort((a, b) => (strip(a) > strip(b) ? 1 : -1));
```

### .map() .join()

I used `.map()` and `.join()` to add the band name to the innerhtml of `#bands`. `.map()` will return an array of `<li>${band}</li>` and when working with innerhtml it is expecting a string so I used `.join('')` to turn the array into a string.
