# Tutoriel - 5

## @showdialog

Programme le Bit Board Rover.

## Étape 1

Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

## Étape 2

Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans la zone de programmation.

```blocks

input.onButtonPressed(Button.A, function () {
})

```
## Étape 3

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:P14||``.

Ajoute le bloc ``||variables: définir P14 ||`` dans le bloc ``||input:lorsque le bouton A est pressé||``.

Remplace la valeur ``||variables:0||`` par ``||variables:50||``.

```blocks

let P14 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
})


```

## Étape 4

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:P13||``.

Ajoute le bloc ``||variables: définir P13 ||`` sous le bloc ``||variables: définir P14 ||``.

Remplace la valeur ``||variables:0||`` par ``||variables:50||``.

```blocks

let P14 = 0
let P13 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
    P13 = 50
})

```

## Étape 5

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||variables: définir P13 ||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: P14 ||``.

```blocks

let P14 = 0
let P13 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
    P13 = 50
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, P14)
})

```
## Étape 6

Ajoute le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo: spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: P13 ||``.

```blocks

let P14 = 0
let P13 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
    P13 = 50
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, P14)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, P13)
})


```

## Étape 7

Ajoute le bloc ``||basic:pause||`` sous le bloc ``||continuousservo:spin other way||``.

Remplace la valeur ``||basic:50||`` par ``||basic:2000||``.

```blocks

let P14 = 0
let P13 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
    P13 = 50
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, P14)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, P13)
    basic.pause(2000)
})

```

## Étape 8

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) sous le bloc ``||basic:pause||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

let P14 = 0
let P13 = 0
input.onButtonPressed(Button.A, function () {
    P14 = 50
    P13 = 50
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, P14)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, P13)
    basic.pause(2000)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
})

```
## Étape 9

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.


```package

tinkertanker/pxt-continuous-servo

```
