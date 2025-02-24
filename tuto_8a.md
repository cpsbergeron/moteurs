# Tutoriel 8A

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

Le valeur pour l'émetteur et le récepteur doit être la même.

Il s'agit de la fréquence radio qui sera utilisée par les deux micro:bit.


## Étape 4

Ajoute le bloc ``||basic:montrer icone||`` sous le bloc ``||radio:radio définir groupe||``.

Sélectionn le crochet comme icone.

```blocks

radio.setGroup(1)
basic.showIcon(IconNames.Yes)
basic.forever(function () {
	
})

```

## Étape 5

Ajoute le bloc ``||radio:send string||`` (trad. : envoyer une ligne) dans le bloc ``||input:lorsque le bouton A est pressé||``.

```blocks

input.onButtonPressed(Button.A, function () {
    radio.sendString("")
})

```

## Étape 6

Modifie le bloc ``||radio:send string||``.

Écris le mot ``||radio:1||`` dans le bloc. (1 = Avancer)

```blocks

input.onButtonPressed(Button.A, function () {
    radio.sendString("Avancer")
})

```

## Étape 7

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||radio:send string||``.

Dessine une flèche qui pointe vers le haut.

```blocks

input.onButtonPressed(Button.A, function () {
    radio.sendString("Avancer")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})

```

## Étape 8

Dupplique le bloc ``||input:lorsque le bouton A est pressé||``.

Modifie la valeur ``||input:A||`` pour ``||input:B||``.

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("Avancer")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})

```

## Étape 9

Modifie la valeur ``||radio:Avancer||`` pour ``||input:Arreter||`` **(sans accent)**.

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("Arreter")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})

```

## Étape 10

Modifie le bloc ``||basic:montrer LEDs||``.

Remplace la flèche qui pointe vers le haut par une flèche qui pointe vers le bas.

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("Arreter")
    basic.showLeds(`
        . . # . .
        . . # . .
        # . # . #
        . # # # .
        . . # . .
        `)
})

```

## @showdialog 

Félicitations! Tu as terminé de programmer l'émetteur.

Pour tester, télécharge la programmation dans le micro:bit.