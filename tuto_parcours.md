# Tutoriel Parcours

## @showdialog

Programme le Bit Board Rover pour réaliser les différents parcours demandés.

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

Ne fais pas cette étape ! :)

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P0, 0)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P0, 0)
})
input.onButtonPressed(Button.B, function () {
    basic.pause(0)
})
ContinuousServo.turn_off_motor(DigitalPin.P0)
basic.forever(function () {
    ContinuousServo.turn_off_motor(DigitalPin.P0)
})


```

## Étape 4

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.


```package

tinkertanker/pxt-continuous-servo

```
