# Project 19 - Webcam Fun

## Demo

https://andycodes.io/JavaScript30/19%20-%20Webcam%20Fun/

## Objective

For project 19, I made a photobooth app that using the webcam to take pictures. It includes a green screen effect that removes colors with in the range of the RBG, which is controlled with the lever.

## Javascript

### Access to webcam

To get access to the webcam:

```
function getVideo() {
  navigator.mediaDevices
    .getUserMedia({ video: true, audio: false })
    .then(localMediaStream => {
      video.srcObject = localMediaStream;
      video.play();
    })
    .catch(err => {
      console.error(`OH NO!!!`, err);
    });
}
```

`navigator.mediaDevices.getUserMedia({ video: true, audio: false })` will return a promise which we then use `.then(localMediaStream => {video.srcObject = localMediaStream; video.play(); })` to display the webcam feed.

### Take a photo

```
function takePhoto() {
  // played the sound
  snap.currentTime = 0;
  snap.play();

  // take the data out of the canvas
  const data = canvas.toDataURL('image/jpeg');
  const link = document.createElement('a');
  link.href = data;
  link.setAttribute('download', 'handsome');
  link.innerHTML = `<img src='${data}' alt="Handsome Man" />`;
  strip.insertBefore(link, strip.firstChild);
}
```

To take a photo, you take the data out of the canvas using `const data = canvas.toDataURL('image/jpeg');` and this will return "Base64" which is a text representation of the image.

### Applying a filter

To apply the filter, you would take the pixels out of the data, then change the value, and then would put new pixels value back

```
function paintToCanvas() {
  const width = video.videoWidth;
  const height = video.videoHeight;
  canvas.width = width;
  canvas.height = height;

  return setInterval(() => {
    ctx.drawImage(video, 0, 0, width, height);

    // take the pixels out
    let pixels = ctx.getImageData(0, 0, width, height);

    // mess with them
    // pixels = redEffect(pixels);
    // pixels = rgbSplit(pixels);
    // ctx.globalAlpha = 0.1;
    pixels = greenScreen(pixels);

    // put them back
    ctx.putImageData(pixels, 0, 0);
  }, 16);
}
```
