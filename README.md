# Environmental Sensor Data Display

## Introduction
When you press ``||input: button A||``, ``||logic: if||`` the ``||gatorEnvironment: carbon dioxide||`` is ``||logic: less||`` than 500 how a down arrow else show an up arrow. Things to think about. Draw a picture to help think about what you want to happen. When you're ready press the NEXT button to start.

## Step 1
When you turn the micro:bt on, ``||gatorEnvironment: initialize||`` the environmental sensor

```blocks
gatorEnvironment.beginEnvironment()
```

## Step 2 
Code your micro:bit to take a ``||gatorEnvironment: carbon dioxide||`` reading when ``||input: button A||`` is pressed and ``||basic: show||`` that reading on the micro:bit. 

```blocks
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
})
```

## Step 3
Now code your micro:bit to display a ``||basic: down arrow||`` ``||logic: if||``  ``||gatorEnvironment: carbon dioxide||`` 
is ``||logic: less than||`` 500.

```blocks
gatorEnvironment.beginEnvironment()
input.onButtonPressed(Button.A, function () {
       basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2)) 
       if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
        basic.showIcon(IconNames.Sword)
    }
})
```

## Step 4
Now code your micro:bit to display ``||basic: up arrow||`` if  ``||gatorEnvironment: carbon dioxide||`` 
is ``||logic: greater than||`` 500.  


```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
    if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
        basic.showIcon(IconNames.Sword)
    } else {
        basic.showLeds(`
            . . # . .
            . # # # .
            . . # . .
            . . # . .
            . . # . .
            `)
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
        basic.showString("Temp")
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
        basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            basic.showIcon(IconNames.Sword)
        } else {
            basic.showLeds(`
                . . # . .
                . # # # .
                . . # . .
                . . # . .
                . . # . .
                `)
        }
    }
})
```

## Step 9
``||basic: wait||`` 10 seconds in between each time the sensor takes a reading

```blocks
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        basic.showNumber(gatorEnvironment.getMeasurement(measurementType.eCO2))
        if (gatorEnvironment.getMeasurement(measurementType.eCO2) < 500) {
            basic.showIcon(IconNames.Sword)
        } else {
            basic.showLeds(`
                . . # . .
                . # # # .
                . . # . .
                . . # . .
                . . # . .
                `)
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






