# repeatAudio
A simple function which repeats an audio file a specified number of times with an optional interval between repeats.

______

## The `repeatAudio()` function

```
const repeatAudio = (soundEffect, repeats, interval = 0) => {

  for (let i = 0; i < repeats; i++) {

    let duration = (soundEffect.duration * 1000);

    setTimeout(() => {
      soundEffect.currentTime = 0;
      soundEffect.play();
    }, (i * (duration + interval)));
  }
}
```

______

## Invoking the `repeatAudio()` function

### Without an interval:
    repeatAudio(letterReveal, 5);

### With an interval:
    repeatAudio(letterReveal, 5, 500);

### With a negative interval:
    repeatAudio(letterReveal, 5, -60);
    
    
______

## Alternative approach (no *interval* enabled, but *playback* is more reliable)

```
const tyrannosaurusRoar = new Audio('https://interactive-examples.mdn.mozilla.net/media/cc0-audio/t-rex-roar.mp3');

/** N.B. This line:
  
    setTimeout(() => console.log(tyrannosaurusRoar.duration), 1000);
  
    tells us that the sound file duration is 2.142 seconds **/

const tyrannosaurusRoarDuration = 2142;
tyrannosaurusRoar.loop = true;
setTimeout(() => tyrannosaurusRoar.loop = false, (tyrannosaurusRoarDuration * 3));
tyrannosaurusRoar.play();
```

