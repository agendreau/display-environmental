# Environmental Sensor Data Display

## Introduction
When you press ``||input: button A||``, turn on ``||Neopixel: green lights||`` ``||logic: if||`` the ``||gatorEnvironment: carbon dioxide||`` is ``||logic: less||`` than 500  and ``||Neopixel: yellow lights||`` if the ``||gatorEnvironment: carbon dioxide||`` is ``||logic: more than||`` 500. Things to think about. Which pin controls the Lights on the gator:bit? How mand LEDs are on the gator:bit? Draw a picture to help think about the logic.

## Step 1
``||basic: Initialize||`` the LEDs to that ``||variables: strip||`` can control them and initialize the environmental sensor

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
gatorEnvironment.beginEnvironment()
```

## Step 2 
Code your micro:bit to take a carbon dioxide reading when ``||input: button A||`` is pressed. Set the ``||neopixel: brightness||`` of the strip to 50, so the lights are not extremely bright.

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
    strip.setBrightness(50)
})
```

## Step 3
Now code your micro:bit to display ``||Neopixel: green lights||`` when  ``||gatorEnvironment: carbon dioxide||`` 
is ``||logic: less than||`` 500.

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
        strip.setBrightness(50)
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            strip.showColor(neopixel.colors(NeoPixelColors.Green))
        } 
})
```

## Step 4
Now code your micro:bit to display ``||Neopixel: yellow lights||`` when  ``||gatorEnvironment: carbon dioxide||`` 
is ``||logic: greater than||`` 500.  


```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
        strip.setBrightness(50)
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            strip.showColor(neopixel.colors(NeoPixelColors.Green))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Yellow))
        }
})
```
## Step 5
``|Download your code|`` and try it out

## Step 6
Modify the program so that when you press ``||input: button B||``, 
if the ``||gatorEnvironment: temperature||`` is greater than 75 F, 
the gator:bit ``||music: plays a song||``. 

```blocks
input.onButtonPressed(Button.B, function () {
    if (gatorEnvironment.getMeasurement(measurementType.degreesF) > 75) {
        music.beginMelody(music.builtInMelody(Melodies.Chase), MelodyOptions.Once)
    }
})
```

## Step 7
``|Download|`` your code and try it out

## Step 8
Modify either the lights or music to ``||Loops: repeat||`` 5 times

```blocks
input.onButtonPressed(Button.A, function () {
     for (let i = 0; i < 5; i++) {
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            strip.showColor(neopixel.colors(NeoPixelColors.Green))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Yellow))
        }
    }
})
```

## Step 9
``||basic: wait||`` 10 seconds in between each time the sensor takes a reading
```blocks
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        let strip: neopixel.Strip = null
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            strip.showColor(neopixel.colors(NeoPixelColors.Green))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Yellow))
        }
        basic.pause(10000)
    }
})
```
## Step 10
``|Download|`` the code and try it out.


```package
gatorEnvironment=github:sparkfun/pxt-gator-environment
neopixel=github:microsoft/pxt-neopixel
```






