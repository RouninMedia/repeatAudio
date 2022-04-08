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

**Without an interval:**
    repeatAudio(letterReveal, 5);

**With an interval:**
    repeatAudio(letterReveal, 5, 500);

**With a negative interval:**
    repeatAudio(letterReveal, 5, -60);
