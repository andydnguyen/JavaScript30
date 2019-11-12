# Project 20 - Speech Detection

## Demo

https://andycodes.io/JavaScript30/20%20-%20Speech%20Detection

## Objective

For project 20, I built a speech recognition in the browser. While it's not perfect, it's actually really impressive that you can do this without any libraries or external APIs, just do it straight in the browser.

## Javascript

speech recognition from the browser:

```
window.SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;

const recognition = new SpeechRecognition();
```

`recognition.interimResults = true;` allows the the speech recognition to run while you are still talking

This would grab the transcript from the browser:

```
recognition.addEventListener('result', e => {
  const transcript = Array.from(e.results)
    .map(result => result[0])
    .map(result => result.transcript)
    .join('');

  p.textContent = transcript;
});
```

This would create a new paragraph tag then append it words:

```
if (e.results[0].isFinal) {
  p = document.createElement('p');
  words.appendChild(p);
}
```

`recognition.addEventListener('end', recognition.start);` allows the speech recognition to run again after the the inital speech recognition was ran.
