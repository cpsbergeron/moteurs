# Tutoriel 1

## Étape #

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : fermer le moteur) dans le bloc ``||basic:au démarrage||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)

```

```package

continuous-servo=github:tinkertanker/pxt-continuous-servo

```
