# Tutoriel 7

## @showdialog

Programme le Bit Board Rover à l'aide de fonctions déterminées.

## Étape 1

Supprime les blocs ``||basic:toujours||`` et ``||basic:au démarrage||``.

## Étape 2

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Démarrer||``.

```blocks

function Démarrer () {
	
}

```

## Étape 3

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Démarrer||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Démarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 4

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).
Choisis le crochet comme icône.

Ajoute le bloc ``||basic:pause (ms)||`` sous le bloc ``||basic:montrer l'icône||``.
Remplace ``||basic:100||`` par ``||basic:1000||``.

```blocks

function Démarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
    basic.pause(1000)
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

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:100||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 100)
}
function Démarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
}

```

## Étape 7

Ajoute un bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:100||``.

```blocks

function Avancer (ms: number) {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 100)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 100)
}
function Démarrer () {
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
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 100)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 100)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Démarrer () {
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
function Démarrer () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.Yes)
}

```

## Étape 10

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arrêter||``.

```blocks

function Arrêter () {
	
}

```

## Étape 11

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arrêter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Arrêter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 12

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le X comme icône.

```blocks

function Arrêter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}

```

## Étape 13

Duplique la fonction ``||functions:Avancer||``.
Renomme celle-ci ``||functions:Reculer||``.
Apporte les modifications nécessaires.

## Étape 14

Crée la fonction ``||functions:Gauche||``.
Regarde la programmation dans ton cahier.
Ajoute également une flèche pour indiquer la direction.

## Étape 15

Duplique la fonction ``||functions:Gauche||``.
Renomme celle-ci ``||functions:Droite||``.
Apporte les modifications nécessaires.

## Étape 16

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

Chaque séquence doit contenir le bloc ``||functions:appel Démarrer||`` suivi des autres actions à réaliser.

Les fonctions ``||functions:appel Avancer||`` et ``||functions:appel Reculer||`` doivent être suivies du bloc ``||functions:appel Arrêter||`` pour permettre au robot de s'arrêter avant de réaliser une autre action.

Pour un déplacement plus fluide du bolide, il est recommendé d'ajouter le bloc ``||basic:pause 500 (ms)||`` entre chaque action.

## @showdialog

Regarde attentivement l'animation pour créer une séquence de programmation avec les fonctions.

![MicroSeb](https://github.com/cpsbergeron/moteurs/blob/master/bolide_fonction.gif?raw=true)


## Étape 18

Voici d'autres blocs pour t'aider à créer les nouvelles fonctions.

```blocks

let vitesse = 0
input.onButtonPressed(Button.B, function () {
    vitesse = 100
    basic.pause(100)
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
