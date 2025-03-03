# Tutoriel Récepteur B

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

Ajoute le bloc ``||basic:montrer icône||`` sous le bloc ``||radio:radio définir groupe||``.

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
ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)

```

## Étape 6

Crée une ``||variables: fonction||`` et donne-lui le nom ``||variables:Vitesse||``.

Remplace la valeur ``||variables: 0||`` par ``||variables: 50||``.

Ajoute le bloc ``||variables: définir Vitesse||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. éteindre les moteurs).

```blocks

basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
let Vitesse = 50

```

## Étape 7

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||``

```blocks

function Avancer {
}

```

## Étape 8

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables:Vitesse||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
}

let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50

```

## Étape 9

Ajoute le bloc ``||continuousservo:spin the other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables:Vitesse||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, Vitesse)
}
let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50

```
## Étape 10

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin the other way||`` (trad. : tourner dans l'autre sens).

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, Vitesse)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50

```

## Étape 11

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arreter||`` (** sans accent **).

```blocks

function Arreter () {
	
}

```

## Étape 12

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arreter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 13

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le X comme icône.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}

```

## Étape 14

Glisse le bloc  ``||radio:quand une donnée est reçue||`` dans la zone de programmation.

Ajoute le bloc ``||logic:si alors||`` sous le bloc ``||radio:quand une donnée est reçue||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (true) {
    	
    }
})

```

## Étape 15

Modifie le bloc ``||logic:si alors||``.

Remplace la valeur ``||logic:vrai||`` par le bloc ``||logic:" " = " "||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if ("" == "") {
    	
    }
})

```

## Étape 16

Glisse le bloc ``||variables:receivedString||`` dans l'espace de gauche.

Écris la valeur ``||logic:Avancer||`` dans l'espace de droite.


```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
    	
    }
})
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, Vitesse)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}
let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50


```

## Étape 16

Ajoute le bloc ``||functions:appel Avancer||`` dans le bloc ``||logic:si alors||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer()
    }
})
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, Vitesse)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}
let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50

```

## Étape 17

Duplique le bloc ``||logic:si alors||`` et glisse celui-ci sous le premier bloc ``||logic:si alors||``.

Remplace la valeur ``||logic:Avancer||`` par la valeur Arreter.

Remplace le bloc ``||functions:appel Avancer||`` par le bloc ``||functions:appel Arreter||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer()
    }
    if (receivedString == "Arreter") {
        Arreter()
    }
})
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, Vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, Vitesse)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}
let Vitesse = 0
basic.showIcon(IconNames.Yes)
radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)
Vitesse = 50

```


## @showdialog 

Félicitations! Tu as terminé de programmer l'émetteur.

Pour tester, télécharge la programmation dans le micro:bit.