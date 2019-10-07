# Practice 1 - Drum Kit

## Objective
Build a drum kit that can be control via keyboard.

## Procedure
We start off with prepared HTML. Important details are:

### Markup
Use of custom `data-key` attribute for keys&hellip;

```
<div class="keys">
  <div data-key="65" class="key">
    <kbd>A</kbd>
    <span class="sound">clap</span>
  </div>
  ...
</div>
```

&hellip; and for audio, too.

```
<audio data-key="65" src="sounds/clap.wav"></audio>
<audio data-key="83" src="sounds/hihat.wav"></audio>
```

### JavaScript

First, wait for user input
```
window.addEventListener('keydown', playSound);
```

If user presses a key, it'll trigger `playSound` function and pass `KeyboardEvent` as a parameter.

Next we want to play sounds associated with given keys.

```
function playSound(e) {
  console.log(e); // -> KeyboardEvent {isTrusted: true, key: "s", code: "KeyS", location: 0, ctrlKey: false…}

  // check if pressed key has associated audio/key
  var key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
  var audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

  // if not, ignore this key
  if (!audio) return;

  // if it has:
    // 1 - add class playing for style modification
    // 2 - reset audio, so we can play again before it finished
    // 3 - play that sound
  key.classList.add('playing'); // 1
  audio.currentTime = 0;        // 2
  audio.play();                 // 3
};
```

For styling purposes we added class `.playing`. We also need to put it away after the transition. We can leverage `transitionend` event listener, so we don't have to worry about keeping value in CSS and JS in sync.

```
// build an array of keys
const keys = Array.from(document.querySelectorAll('.key'));

// assign event listener to all of them. This event listener would then call removeTransition function
keys.forEach(key => key.addEventListener('transitionend', removeTransition));
```

`transitionend` will fire for every CSS property. We are going to choose only one, generally the longest one. In our case we've chosen `transform`. So this function will ignore all the `transitionend`s except `transform`. When that one finishes, we'll remove the modifier class.

```
function removeTransition(e) {
  if (e.propertyName !== 'transform') return;
  e.target.classList.remove('playing');
  // this.classList.remove('playing'); // also working
}
```

## TIL
- [http://keycode.info/](http://keycode.info/) - site showing key codes
