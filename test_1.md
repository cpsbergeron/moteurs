# Test

```blockconfig.global
input.onButtonPressed(Button.A, function () {
    basic.showString("Hello!")
})
basic.showIcon(IconNames.Heart)
```

## @showdialog

Programme le Bit Board Rover.

## Étape 1

Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

## Étape 2

Ajoute un bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||input:lorsque le bouton A est pressé||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:25||``.

```blocks

input.onButtonPressed(Button.A, function () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
})

```

```package

tinkertanker/pxt-continuous-servo

```