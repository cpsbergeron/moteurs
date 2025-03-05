# Tutoriel 6

## @showdialog

Programme le capteur de distance.

## Étape 1

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:distance||``.

Ajoute le bloc ``||variables: définir vitesse ||`` dans le bloc ``||basic:toujours||``.


```blocks

let distance = 0
basic.forever(function () {
    distance = 0
})


```
## Étape 2

Modifie le bloc ``||variables: définir distance||``.

Remplace la valeur ``||variables: 0||`` par le bloc ``||sonar:sonde de distance||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P0,
    PingUnit.MicroSeconds
    )
})


```

## Étape 3

Modifie le bloc ``||sonar: sonde de distance|||``.

La valeur ``||sonar:P0||`` pour ``||sonar:ping trig||`` demeure la même.

Remplace la valeur ``||sonar:P0||`` de ``||sonar:echo||`` pour ``||sonar:P1||``.

Remplace la valeur ``||sonar:us||`` de ``||sonar:unit||`` pour ``||sonar:cm||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
})

```

```package

tinkertanker/pxt-continuous-servo
microsoft/pxt-sonar

```


