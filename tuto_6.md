# Tutoriel 2

## @showdialog

Programme le Bit Board Rover à l'aide de fonctions déterminées.


## Étape 1

Supprime le bloc ``||basic:toujours||``.

## Étape 2

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Demarrage||`` ** (sans accent) **.

```blocks

function Avancer () {
	
}

```

## Étape 3

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Demarrage||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

function Demarrage () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
}

```

## Étape 4

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le crochet comme icône.

```blocks

function Demarrage () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    basic.showIcon(IconNames.Yes)
}

```

## Étape 5

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:vitesse||``.

Ajoute le bloc ``||variables: définir vitesse ||`` sous le bloc ``||basic:montrer l'icône||``.

Remplace la valeur ``||variables:0||`` par ``||variables:25||``.

```blocks

function Demarrage () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    basic.showIcon(IconNames.Yes)
    vitesse = 25
}

```

## Étape 6

Crée une ``||functions: fonction||`` et donne-lui le nom ``||variables:Avancer||``.

```blocks

function Avancer () {
	
}

```

## Étape 7

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||variables: définir vitesse ||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: vitesse ||``.

```blocks

let vitesse = 0
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, vitesse)
}

```

## Étape 8

Ajoute le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par le bloc ``||variables: vitesse ||``.

```blocks

let vitesse = 0
function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P14, vitesse)
}

```

## Étape 9

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arrter||`` ** (sans accent) **.

```blocks

function Arreter () {
	
}

```

## Étape 10

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arreter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
}

```

## Étape 11

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Choisis le X comme icône.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    basic.showIcon(IconNames.No)
}

```
## Étape 12

Ajoute le bloc ``||functions:appel Demarrage||`` dans le bloc ``||basic:au démarrage||``.

Ajoute le bloc ``||functions:appel Avancer||`` sous le bloc ``||functions:appel Demarrage||``.

Ajoute le bloc ``||basic:pause||`` sous le bloc ``||functions:appel Avancer||``.

Remplace la valeur ``||basic:100||`` par ``||basic:2000||``.

Ajoute le bloc ``||functions:appel Arreter||`` sous le bloc ``||basic:pause||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, vitesse)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P14, vitesse)
}
function Demarrage () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    basic.showIcon(IconNames.Yes)
    vitesse = 50
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    basic.showIcon(IconNames.No)
}
let vitesse = 0
Demarrage()
Avancer()
basic.pause(2000)
Arreter()

```

## Étape 13

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

continuous-servo=github:tinkertanker/pxt-continuous-servo

```
