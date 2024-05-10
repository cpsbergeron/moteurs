# Tutoriel 1

## Étape 1

Supprime le bloc ``||basic:toujours||``.

Ajoute le bloc ``||radio:radio définir groupe||`` dans le bloc ``||basic:au démarrage||``.

Remplace la valeur ``||radio:1||`` par le ``||radio:# de ton ensemble||``.

```blocks

radio.setGroup(1)

```

## Étape 2

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : fermer le moteur) bloc sous le bloc ``||radio:radio définir groupe||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P13||`` et ``||continuousservo:P14||``.

```blocks

radio.setGroup(1)
ContinuousServo.turn_off_motor(DigitalPin.P13)
ContinuousServo.turn_off_motor(DigitalPin.P14)

```

```package

continuous-servo=github:tinkertanker/pxt-continuous-servo

```
