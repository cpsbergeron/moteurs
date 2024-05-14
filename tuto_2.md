# Tutoriel 2

## @showdialog

Programme le Bit Board Rover pour qu'il recule de quelques cm.

## Étape 1

Supprime le bloc ``||basic:toujours||``.

## Étape 2

Ajoute le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) dans le bloc ``||basic:au démarrage||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:25||``.

```blocks

ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 25)

```
## Étape 3

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par ``||continuousservo:25||``.

```blocks

ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 25)
ContinuousServo.spin_other_way_with_speed(AnalogPin.P14, 25)

```

## Étape 4

Ajoute le bloc ``||basic:pause||`` sous le bloc ``||continuousservo:spin other way||``.

Remplace la valeur ``||basic:100||`` par ``||basic:2000||``.

```blocks

ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 25)
ContinuousServo.spin_other_way_with_speed(AnalogPin.P14, 25)
basic.pause(2000)


```

## Étape 5

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : fermer les moteurs) sous le bloc ``||basic:pause||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 25)
ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
basic.pause(2000)
ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)


```
## Étape 6

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

continuous-servo=github:tinkertanker/pxt-continuous-servo

```
