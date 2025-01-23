# Tutoriel 3

## @showdialog

Programme le Bit Board Rover.

## Étape 1

Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

## Étape 2

Ajoute un bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||input:lorsque le bouton A est pressé||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:50||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 50)
})

```

## Étape 3

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

La valeur ``||continuousservo:0||`` demeure la même.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 0)
})

```

## Étape 4

Ajoute le bloc ``||basic:pause||`` sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||basic:100||`` par ``||basic:675||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 0)
    basic.pause(675)
})

```

## Étape 5

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) sous le bloc ``||basic:pause||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 0)
    basic.pause(675)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
})


```
## Étape 6

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

tinkertanker/pxt-continuous-servo

```
