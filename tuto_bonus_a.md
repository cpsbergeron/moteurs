# Tutoriel 5

## @showdialog

Programme le Bit Board Rover pour réaliser les différents trajets demandés.

## Étape 1

Reproduis la programmation du **Bolide A**.

```blocks

input.onButtonPressed(Button.A, function () {

})

```

## Étape 2

Reproduis la programmation du **Bolide B**.

```blocks

input.onButtonPressed(Button.B, function () {

})

```

## Étape 3

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

## Étape 4

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.


```package

tinkertanker/pxt-continuous-servo

```
