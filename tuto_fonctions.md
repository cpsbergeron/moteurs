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
## @showdialog

Regarde attentivement l'animation pour créer la fonction ``||functions: Avancer||`` du bolide.

![MicroSeb](https://github.com/cpsbergeron/moteurs/blob/master/fonction_avancer.gif?raw=true)

## Étape 5

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||`` et ajoute l'élément ``||variables:ms||`` (onglet Nombres).

```blocks

function Avancer (ms: number) {
}

```

## Étape 6

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:50||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
}

```

## Étape 7

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:-50||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -50)
}
function Demarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
}

```
## Étape 8

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin one way||``.

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -50)
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
}

```

## Étape 9

Ajoute le bloc ``||basic:pause (ms)||`` sous le bloc ``||basic:montrer LEDs||``.

Glisse le bloc ``||variables: ms ||`` dans le bloc ``||basic:pause (ms)||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 50)
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, -50)
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
}

```

## Étape 10

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arreter||`` (** sans accent **).

```blocks

function Arreter () {
	
}

```

## Étape 11

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arreter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 12

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

Crée la fonction ``||functions:Pivoter vers la gauche||``.
Regarde la programmation dans ton cahier.
Ajoute également une flèche pour indiquer la direction.

## Étape 15

Duplique la fonction ``||functions:Pivoter vers la gauche||``.
Programme la fonction ``||functions:Pivoter vers la droite||``.
Regarde la programmation dans ton cahier.
Ajoute également une flèche pour indiquer la direction.

## Étape 16

Crée la fonction ``||functions:Pivoter sur lui-même||``.
Regarde la programmation dans ton cahier.
Ajoute également une flèche pour indiquer la direction.

## Étape 17

Glisse les blocs ``||input:lorsque le bouton A est pressé||``, ``||input:lorsque le bouton B est pressé||`` et ``||input:lorsque le bouton A+B est pressé||`` dans la zone de programmation.

```blocks

input.onButtonPressed(Button.A, function () {
	
})
input.onButtonPressed(Button.B, function () {
	
})
input.onButtonPressed(Button.AB, function () {
	
})

```

## @showdialog

Chaque séquence doit contenir le bloc ``||functions:appel Demarrer||`` suivi des autres actions à réaliser.

Les fonctions ``||functions:appel Avancer||`` et ``||functions:appel Reculer||`` doivent être suivies du bloc ``||functions:appel Arreter||`` pour permettre au robot de s'arrêter.

Pour un déplacement plus fluide du bolide, il est recommendé d'ajouter le bloc ``||basic:pause 500 (ms)||`` entre chaque action.

## @showdialog

Regarde attentivement l'animation pour créer une séquence de programmation avec les fonctions.

![MicroSeb](https://github.com/cpsbergeron/moteurs/blob/master/bolide_fonction.gif?raw=true)


## Étape 18

Voici d'autres blocs pour t'aider à créer les nouvelles fonctions.

```blocks

input.onButtonPressed(Button.B, function () {
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P0, 0)
    basic.showString("Hello!")
    basic.showNumber(0)
    basic.clearScreen()
})

```

## Étape 19

Crée maintenant les séquences demandées à l'aide des fonctions.

```package

tinkertanker/pxt-continuous-servo

```
