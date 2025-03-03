# Tutoriel 8B

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

Ajoute le bloc ``||basic:montrer icone||`` sous le bloc ``||radio:radio définir groupe||``.

Sélectionne le crochet comme icone.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)


```

## Étape 5

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) sous le bloc ``||basic:montrer icone||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)
ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)

```

## Étape 6

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||`` et ajoute l'élément ``||variables:ms||`` (onglet Nombres).

```blocks

function Avancer (ms: number) {
}

```

## Étape 7

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:25||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
}

```

## Étape 8

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:-25||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
}

```
## Étape 9

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin one way||``.

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```

## Étape 10

Ajoute le bloc ``||basic:pause (ms)||`` sous le bloc ``||basic:montrer LEDs||``.

Glisse le bloc ``||variables: ms ||`` dans le bloc ``||basic:pause (ms)||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}

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
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showLeds(`
        # . . . #
        . # . # .
        . . # . .
        . # . # .
        # . . . #
        `)
}
radio.setGroup(1)
basic.showIcon(IconNames.Yes)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)

```

## Étape 16

Ajoute le bloc ``||functions:appel Avancer||`` dans le bloc ``||logic:si alors||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer(1)
    }
})
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showLeds(`
        # . . . #
        . # . # .
        . . # . .
        . # . # .
        # . . . #
        `)
}
radio.setGroup(1)
basic.showIcon(IconNames.Yes)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)


```

## Étape 17

Duplique le bloc ``||logic:si alors||`` dans la zone de programmation.

Remplace la valeur ``||logic:Avancer||`` par la valeur Arreter.

Remplace le bloc ``||functions:appel Avancer||`` par le bloc ``||functions:appel Arreter||``.

```blocks

radio.onReceivedString(function (receivedString) {
    if (receivedString == "Avancer") {
        Avancer(1)
    }
    if (receivedString == "Arreter") {
        Arreter()
    }
})
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -25)
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showLeds(`
        # . . . #
        . # . # .
        . . # . .
        . # . # .
        # . . . #
        `)
}
radio.setGroup(1)
basic.showIcon(IconNames.Yes)
ContinuousServo.turn_off_motor(DigitalPin.P14)
ContinuousServo.turn_off_motor(DigitalPin.P13)


## Étape 18

Modifie le bloc ``||functions:appel Avancer||``.

Remplace la valeur ``||functions:1||`` par ``||functions:1000||``.

```

## @showdialog 

Félicitations! Tu as terminé de programmer l'émetteur.

Pour tester, télécharge la programmation dans le micro:bit.