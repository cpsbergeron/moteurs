# Défi supplémentaire

## @showdialog

Programme le Bit Board Rover pour qu'il réalise le trajet demandé.

## Étape 1

Utilise le plus de blocs possible.

```blocks

basic.showIcon(IconNames.Heart)
let vitesse = 0
ContinuousServo.spin_one_way_with_speed(AnalogPin.P13, 0)
ContinuousServo.spin_other_way_with_speed(AnalogPin.P14, 0)
basic.pause(0)
ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)


```
## Étape 2

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

tinkertanker/pxt-continuous-servo

```