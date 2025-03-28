# Tutoriel - Rover lifter 2

## @showdialog

Programme le Rover Lifter.

## Étape 1

Supprime le bloc ``||basic:toujours||``.

## Étape 2

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||basic:au démarrage||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)

```

## Étape 3

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le crochet comme icône.

```blocks

ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
basic.showIcon(IconNames.Yes)
}

```

## Étape 4

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||``

```blocks

function Avancer {
}

```

## Étape 5

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:50||``.

```blocks

function Avancer {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
}

```

## Étape 6

Ajoute un bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:50||``.

```blocks

function Avancer {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
}

```

## Étape 7

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin other way||``.

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```


## Étape 8

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arrêter||``.

```blocks

function Arrêter () {
	
}

```

## Étape 9

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arrêter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Arrêter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 10

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le X comme icône.

```blocks

function Arrêter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}

```

## Étape 11

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Haut||``.

```blocks

function Haut () {
	
}

```

## Étape 12

Ajoute le bloc ``||pins: régler position servo ||`` dans le bloc ``||functions:Haut||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P0, 180)
}

```

## Étape 13

Modifie le bloc ``||pins: régler position servo ||``.

Remplace la valeur ``||pins: P0 ||`` par ``||pins: P15 ||``.

Remplace la valeur ``||pins: 180 ||`` par ``||pins: 150 ||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}

```

## Étape 14

Duplique le bloc ``||functions:Haut||``.


## Étape 15

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

```package

tinkertanker/pxt-continuous-servo

```
