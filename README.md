# libretto-js
A declarative framework for synchronizing JavaScript with audio playback.

# How it Works
Libretto uses [Howler](https://github.com/goldfire/howler.js) to access the browser's Web Audio API and fall back on HTML5 Audio specifications, then abstracts this one layer further, giving you playback and seek controls over a Libretto object, where you can bind JavaScript as well.

## For Example:
```
let moose = new Libretto({ mp3: "./media/moose.mp3"});
moose.bind('START', function() {
  console.log("Hello, world!");
  });
moose.play();
```

This will print "Hello, world!" to the console the moment audio starts to play.`'START'` is one of Libretto's built-in audio landmarks. Others include `'END'`, which fires as audio playback completes; `'STOP'`, which fires when audio playback is stopped (like with `moose.stop()`); `'PAUSE'`, which fires when audio is paused; and `'RESUME'`, which fires when audio is resumed from a paused state. This lets you do things like fold up or fade out a part of your site when audio isn't playing without having to modify the site's core logical flow.
