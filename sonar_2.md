# Sonar 2

## @showdialog

Programme le capteur pour aficher la distance.

## Étape 1

Supprime les blocs ``||basic:toujours||`` et ``||basic:au démarrage||``.

## Étape 2

Glisse le bloc ``||loops:chaque (ms)||`` dans la zone de programmation.

Remplace la valeur ``||loops:500||`` par ``||loops:5000||``.

```blocks
loops.everyInterval(5000, function () {
})

```

## Étape 3

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:distance||``.

Ajoute le bloc ``||variables: définir distance ||`` dans le bloc ``||loops:chaque (ms)||``.

```blocks

let distance = 0
loops.everyInterval(5000, function () {
    distance = 0
})

```
## Étape 4

Modifie le bloc ``||variables: définir distance||``.

Remplace la valeur ``||variables: 0||`` par le bloc ``||sonar:sonde de distance||``.

```blocks

let distance = 0
loops.everyInterval(5000, function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P0,
    PingUnit.MicroSeconds
    )
})

```

## Étape 5

Modifie le bloc ``||sonar: sonde de distance|||``.

La valeur ``||sonar:P0||`` de ``||sonar:ping trig||`` demeure la même.

Remplace la valeur ``||sonar:P0||`` de ``||sonar:echo||`` pour ``||sonar:P1||``.

Remplace la valeur ``||sonar:us||`` de ``||sonar:unit||`` pour ``||sonar:cm||``.

```blocks

let distance = 0
loops.everyInterval(5000, function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
})

```

## Étape 6

Ajoute le bloc ``||basic:montrer nombre||`` sous le bloc ``||variables: définir distance ||``.

Remplace la valeur ``||basic:100||`` par le bloc ``||variables: distance ||``.

```blocks

let distance = 0
loops.everyInterval(5000, function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    basic.showNumber(distance)
})

```

## Étape 7

Ajoute le bloc ``||basic:effacer l'écran||`` sous le bloc ``||basic:montrer nombre||``.

```blocks

let distance = 0
loops.everyInterval(5000, function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    basic.showNumber(distance)
    basic.clearScreen()
})

```

## Étape 8

Bravo ! 🎉🎉🎉

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

dstemps=github:microsoft/pxt-sonar

```

