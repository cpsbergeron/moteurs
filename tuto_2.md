# Tutoriel 2

## @showdialog

Programme le Bit Board Rover.

## Étape 1

Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.


## Étape 2

Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans la zone de programmation.

Ajoute un bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||input:lorsque le bouton A est pressé||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:-25||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, -25)
})

```

## Étape 3

Ajoute un bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:25||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, -25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 25)
})


```

## Étape 4

Ajoute le bloc ``||basic:pause||`` sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||basic:100||`` par ``||basic:2000||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, -25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 25)
    basic.pause(2000)
})


```

## Étape 5

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) sous le bloc ``||basic:pause||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, -25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 25)
    basic.pause(2000)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
})


```

```package

tinkertanker/pxt-continuous-servo

```

## Étape 6

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

