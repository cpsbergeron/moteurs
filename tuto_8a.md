# Tutoriel - Émetteur A

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

Glisse le bloc ``||input:lorsque le bouton A est pressé||`` dans la zone de programmation. 

```blocks

input.onButtonPressed(Button.A, function () {
    
})

```

## Étape 6

Ajoute le bloc ``||radio:envoyer la chaîne||`` dans le bloc ``||input:lorsque le bouton A est pressé||``.

```blocks

input.onButtonPressed(Button.A, function () {
    radio.sendString("")
})

```

## Étape 7

Modifie le bloc ``||radio:envoyer la chaîne||``.

Écris le mot ``||radio:Avancer||`` dans le bloc. 

```blocks

input.onButtonPressed(Button.A, function () {
    radio.sendString("Avancer")
})

```

## Étape 8

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||radio:envoyer la chaîne||``.

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

## Étape 9

Duplique le bloc ``||input:lorsque le bouton A est pressé||``.

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

## Étape 10

Remplace le mot ``||radio:Avancer||`` par le mot ``||radio:Arrêter||``.

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("Arrêter")
    basic.showLeds(`
        . . # . .
        . # . # .
        # . # . #
        . . # . .
        . . # . .
        `)
})

```

## Étape 11

Remplace le bloc ``||basic:montrer LEDs||`` par le bloc ``||basic:montrer l'icône||``.

Sélectionne le X comme icône.

```blocks

input.onButtonPressed(Button.B, function () {
    radio.sendString("Arrêter")
    basic.showIcon(IconNames.No)
})

```

## @showdialog 

Les fonctions de l'émetteur et du récepteur doivent être orthographiées de la même façon.

Même accent. Même majuscule. 

Les appellations doivent être identiques.

## @showdialog 

Félicitations! Tu as terminé de programmer l'émetteur.

Pour tester, télécharge la programmation dans le micro:bit.