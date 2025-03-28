# Tutoriel - Émetteur 

## @showdialog

Transforme le micro:bit en émetteur. 

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

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||radio:radio définir groupe||``.

Sélectionne le crochet comme icône.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)


```

## Étape 5

Glisse le bloc ``||input: écran vers le haut||`` dans la zone de programmation.

Ajoute le bloc ``||radio:envoyer la chaîne||`` dans le bloc ``||input: écran vers le haut||``.


```blocks

input.onGesture(Gesture.ScreenUp, function () {
    radio.sendString("")
})
basic.showIcon(IconNames.Yes)
radio.setGroup(1)

```

## Étape 6

Modifie le bloc ``||radio:envoyer la chaîne||``.

Écris le mot ``||text:Avancer||`` dans le bloc. 

```blocks

input.onGesture(Gesture.ScreenUp, function () {
    radio.sendString("Avancer")
})
basic.showIcon(IconNames.Yes)
radio.setGroup(1)

```

## Étape 7

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||radio:envoyer la chaîne||``.

Dessine une flèche qui pointe vers le haut.

```blocks

input.onGesture(Gesture.ScreenUp, function () {
    radio.sendString("Avancer")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})
basic.showIcon(IconNames.Yes)
radio.setGroup(1)

```

## Étape 8

Ajoute les séquences de programmation manquantes.

## Étape 9

Ne fais pas cette étape ! ;)

```blocks

input.onGesture(Gesture.Shake, function () {
    radio.sendString("Arrêter")
    basic.showIcon(IconNames.No)
})
input.onButtonPressed(Button.A, function () {
    basic.pause(100)
})
input.onGesture(Gesture.ScreenUp, function () {
    radio.sendString("Avancer")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})
radio.setGroup(1)
basic.showIcon(IconNames.Yes)

```

