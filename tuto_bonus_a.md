# Tutoriel 5

## @showdialog

Programme le Bit Board Rover pour réaliser les différents parcours.

## Étape 1

Les blocs ont été mélangés.

```blocks

input.onButtonPressed(Button.A, function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
    vitesse = 50
})
let vitesse = 0
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
basic.clearScreen()
basic.forever(function () {
    basic.pause(100)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, vitesse)
    basic.showString("Hello!")
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
})


```

## Étape 2

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.


```package

tinkertanker/pxt-continuous-servo

```
