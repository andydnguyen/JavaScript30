# Project 18 - Adding Up Times with Reduce

## Demo

https://andycodes.io/JavaScript30/18%20-%20Adding%20Up%20Times%20with%20Reduce

Please view on console.

## Objective

For this project, I wanted to learn how to add all the times up. This idea came from having a playlist from youtube and I wanted to see how long the playlist would be.

## JavaScipt

I learned that when we use `document.querySelectorAll('[data-time]')` it would return a nodeList and to turn it into an array I used the spread operator `(...)`

To grab the seconds from the array I wrote:

```
const seconds = timeNodes
  .map(node => node.dataset.time)
  .map(timeCode => {
    const [mins, secs] = timeCode.split(':').map(parseFloat);
    return mins * 60 + secs;
  })
  .reduce((total, vidSeconds) => total + vidSeconds);
```

`timeNodes.map(node => node.dataset.time)` would grab the time stamps from the array

```
.map(timeCode => {
  const [mins, secs] = timeCode.split(':').map(parseFloat);
  return mins * 60 + secs;
})
```

Would take the time stamps and assign the minutes to mins and the seconds to secs based on `timeCode.split(':').map(parseFloat);` and then multipling the mins to 60 and adding the secs.

```
let secondsLeft = seconds;
const hours = Math.floor(secondsLeft / 3600);
secondsLeft = secondsLeft % 3600;

const mins = Math.floor(secondsLeft / 60);
secondsLeft = secondsLeft % 60;

console.log(hours, mins, secondsLeft);
```

The code above, converts the secondsLeft into hours, mins, and seconds.

`Math.floor` would return the largest integer less than or equal to a given number
