# Tutoriel 7

## @showdialog

Programme le Bit Board Rover à l'aide de fonctions déterminées.

## Étape 1

Supprime les blocs ``||basic:toujours||`` et ``||basic:au démarrage||``.

## Étape 2

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Demarrer||`` ** (sans accent) **.

```blocks

function Demarrer () {
	
}

```

## Étape 3

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Demarrer||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 4

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le crochet comme icône.

```blocks

function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
}

```

## Étape 5

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:vitesse||``.

Ajoute le bloc ``||variables: définir vitesse ||`` sous le bloc ``||basic:montrer l'icône||``.

Remplace la valeur ``||variables:0||`` par ``||variables:25||``.

```blocks

let vitesse = 0
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```

## Étape 6

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||`` (onglet Texte) et ajoute l'élément ``||variables:ms||`` (onglet Nombres).

```blocks

function Avancer (ms: number) {
}

```

## Étape 7

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: vitesse ||``.

```blocks

let vitesse = 0
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```

## Étape 8

Ajoute le bloc ``||continuousservo:spin the other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: vitesse ||``.

```blocks

let vitesse = 0
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, vitesse)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```
## Étape 9

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin the other way||``.

Dessine une flèche qui pointe vers le haut.

```blocks

let vitesse = 0
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, vitesse)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```

## Étape 10

Ajoute le bloc ``||basic:pause (ms)||`` sous le bloc ``||basic:montrer LEDs||``.

Remplace la valeur ``||basic: 100||`` par la valeur ``||variables: ms ||``. 

Glisse le bloc ``||variables: ms ||`` dans le bloc ``||basic:pause (ms)||``.

```blocks

let vitesse = 0
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, vitesse)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```

## Étape 11

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arreter||`` ** sans accent **.

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

Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans la zone de programmation.

Ajoute les blocs ``||functions:Demarrer||``, ``||functions:Avancer||`` et ``||functions:Arreter||`` dans le bloc ``||input:lorsque le bouton A est pressé||``.

Remplace la valeur ``||functions:1||`` par ``||functions:1000||``.

```blocks

let vitesse = 0
input.onButtonPressed(Button.A, function () {
    Demarrage()
    Avancer(1)
    Arreter()
})
function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, vitesse)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
    basic.pause(ms)
}
function Demarrage () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}

```

```package

tinkertanker/pxt-continuous-servo

```

## Étape 14

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.


