# Tutoriel Émetteur B

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

Ajoute le bloc ``||basic:montrer icône||`` sous le bloc ``||radio:radio définir groupe||``.

Sélectionne le crochet comme icône.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)


```

## Étape 5

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

Écris le mot ``||radio:Avancer||`` dans le bloc. 

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

Duplique le bloc ``||input:lorsque écran vers le haut||``.

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

## Étape 9

Modifie la valeur ``||input:lorsque écran vers le haut||`` pour ``||input:lorsque secouer||``.

```blocks

input.onGesture(Gesture.Shake, function () {
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

## Étape 10

Modifie la valeur ``||radio:Avancer||`` pour ``||radio:Arreter||`` **(sans accent)**.

```blocks

input.onGesture(Gesture.Shake, function () {
    radio.sendString("Arreter")
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

## Étape 11

Remplace le bloc ``||basic:montrer LEDs||`` par le bloc ``||basic:montrer icone||``.

Sélectionne le X comme icone.

```blocks

input.onGesture(Gesture.Shake, function () {
    radio.sendString("Arreter")
    basic.showIcon(IconNames.No)
})
basic.showIcon(IconNames.Yes)
radio.setGroup(1)


```

## Étape 12

Des blocs ont été ajoutés au tutoriel pour te permettre de le compléter.

```blocks

input.onGesture(Gesture.Shake, function () {
    radio.sendString("Arreter")
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

## @showdialog 

Félicitations! Tu as terminé de programmer l'émetteur.

Pour tester, télécharge la programmation dans le micro:bit.