# Tutoriel - Rover lifter 1

## @showdialog

Programme le Rover Lifter.

## Étape 1

Supprime les blocs ``||basic:au démarrage||`` et ``||basic:toujours||``.

## Étape 2

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Haut||``.

```blocks

function Haut () {
	
}

```

## Étape 3

Ajoute le bloc ``||pins: régler position servo ||`` dans le bloc ``||functions:Haut||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P0, 180)
}

```

## Étape 4

Modifie le bloc ``||pins: régler position servo ||``.

Remplace la valeur ``||pins: P0 ||`` par ``||pins: P15 ||``.

Remplace la valeur ``||pins: 180 ||`` par ``||pins: 150 ||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}

```

## Étape 5

Duplique le bloc ``||functions:Haut||``.

## Étape 6

Remplace la valeur ``||functions:Haut2||`` par la valeur ``||functions:Bas||``.

Remplace la valeur ``||pins: 150 ||`` par ``||pins: 50 ||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}
function Bas () {
    pins.servoWritePin(AnalogPin.P15, 50)
}

```
## Étape 7

Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans la zone de programmation.

```blocks

input.onButtonPressed(Button.A, function () {
})

```

## Étape 8

Glisse le bloc ``||functions:appel Haut||`` dans le bloc ``||input:lorsque le bouton A est pressé||``.

```blocks

input.onButtonPressed(Button.A, function () {
    Haut()
})
function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}

```

## Étape 9

Duplique le bloc ``||input:lorsque le bouton A est pressé||``.

## Étape 10

Remplace la valeur ``||input:A||`` par la valeur ``||input:B||``.

Remplace le bloc ``||functions:appel Haut||`` par le bloc ``||functions:appel Bas||``.

```blocks

input.onButtonPressed(Button.A, function () {
    Haut()
})
function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}
input.onButtonPressed(Button.B, function () {
    Bas()
})
function Bas () {
    pins.servoWritePin(AnalogPin.P15, 50)
}


```

```package

tinkertanker/pxt-continuous-servo

```

## @showdialog

Assure-toi que la pelle mécanique du Rover Lifter soit à environ 1 poutre de hauteur du sol.

Il est possible que les valeurs ``||pins: 50 ||`` et ``||pins: 150 ||`` ne conviennent pas au Rover Lifter.

Apporte les modifications nécessaires.

## Étape 10

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

