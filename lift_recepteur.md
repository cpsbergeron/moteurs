# Tutoriel - Récepteur 

## @showdialog

Transforme le micro:bit en récepteur. 

## Étape 1

Supprime le bloc ``||basic:toujours||``.

## Étape 2

Ajoute le bloc ``||radio:radio définir groupe||`` dans le bloc ``||basic:au démarrage||``.

```blocks

radio.setGroup(1)

```

## Étape 3

Modifie le bloc ``||radio:radio définir groupe||``.

Remplace la valeur ``||radio:1||`` par une valeur entre  ``||radio:1||`` et  ``||radio:255||``.

```blocks

radio.setGroup(1)

```
## @showdialog 

Le valeur pour l'émetteur et la valeur pour le récepteur doivent être la même.

Il s'agit de la fréquence radio qui sera utilisée par les deux micro:bit.


## Étape 4

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||radio:radio définir groupe||``.

Sélectionne le crochet comme icône.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)


```

## Étape 5

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) sous le bloc ``||basic:montrer icône||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)

```

## Étape 6

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||``

```blocks

function Avancer {
}

```

## Étape 7

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par  ``||continuousservo:50||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
}

```

## Étape 8

Ajoute le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||continuousservo:50||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
}

```
## Étape 9

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens).

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```

## Étape 10

Glisse le bloc  ``||radio:quand une donnée est reçue||`` dans la zone de programmation.

Ajoute le bloc ``||logic:si alors||`` sous le bloc ``||radio:quand une donnée est reçue||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (true) {
    	
    }
})

```

## Étape 11

Modifie le bloc ``||logic:si alors||``.

Remplace la valeur ``||logic:vrai||`` par le bloc ``||logic:" " = " "||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if ("" == "") {
    	
    }
})

```

## Étape 12

Glisse le bloc ``||variables:receivedString||`` dans l'espace de gauche.

Écris le mot ``||text:Avancer||`` dans l'espace de droite.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
    	
    }
})

```

## Étape 13

Ajoute le bloc ``||functions:appel Avancer||`` dans le bloc ``||logic:si alors||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer()
    }
})
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```

## Étape 14

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Haut||``.

```blocks

function Haut () {
	
}

```

## Étape 15

Ajoute le bloc ``||pins: régler position servo ||`` dans le bloc ``||functions:Haut||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P0, 180)
}

```

## Étape 16

Modifie le bloc ``||pins: régler position servo ||``.

Remplace la valeur ``||pins: P0 ||`` par ``||pins: P15 ||``.

Remplace la valeur ``||pins: 180 ||`` par ``||pins: 150 ||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
}

```

## Étape 17

Ajoute le bloc ``||basic: montrer l'icône ||`` sous le bloc ``||pins: régler position servo ||``.

Choisis le carré comme icône.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
    basic.showIcon(IconNames.Square)
}


```

## Étape 18

Duplique le bloc ``||logic:si alors||``.

Remplace le mot ``||text:Avancer||`` par le mot ``||text:Haut||``.

Remplace la fonction ``||functions:Avancer||`` par la fonction ``||functions:Haut||``.

```blocks

function Haut () {
    pins.servoWritePin(AnalogPin.P15, 150)
    basic.showIcon(IconNames.Square)
}
radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer()
    }
    if (receivedString == "Haut") {
        Haut()
    }
})
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 50)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```
## Étape 19

Ajoute les séquences de programmation manquantes.

## Étape 20

Ne fais pas cette étape ! ;)

```blocks

let vitesse = 0
basic.forever(function () {
    vitesse = 0
    basic.showString("Hello!")
    basic.clearScreen()
    basic.pause(50)
    pins.servoWritePin(AnalogPin.P0, 180)
    basic.showIcon(IconNames.Heart)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        `)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P0, 0)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P0, 0)
})

```