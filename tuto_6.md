# Tutoriel - 6

## @showdialog

Programme le Bit Board Rover.

## Étape 1

Supprime les blocs ``||basic:toujours||`` et ``||basic:au démarrage||``.

## Étape 2

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Message||``.

```blocks

function Message () {
	
}

```

## Étape 3

Ajoute le bloc ``||basic: afficher texte||`` dans le bloc ``||functions:Message||``.

Remplace le mot ``||basic: Hello!||`` par ``||basic: Bolide||``.

```blocks

function Message () {
    basic.showString("Bolide")
}

```

## Étape 4

Glisse le bloc ``||input: lorsque le bouton A est pressé||`` dans la zone de programmation.

```blocks

function Message () {
    basic.showString("Bolide")
}
input.onButtonPressed(Button.A, function () {
	
})

```

## Étape 5

Ajoute le bloc ``||functions: appel Message||`` dans le bloc ``||input: lorsque le bouton A est pressé||``.

```blocks

function Message () {
    basic.showString("Bolide")
}
input.onButtonPressed(Button.A, function () {
    Message()
})

```

## Étape 6

Ajoute le bloc ``||basic: pause (ms)||`` sous le bloc ``||functions: appel Message||``.

Remplace la valeur ``||basic: 100||`` par ``||basic: pause 1000||``. 

```blocks

function Message () {
    basic.showString("Bolide")
}
input.onButtonPressed(Button.A, function () {
    Message()
    basic.pause(1000)
})


```
## Étape 7

Ajoute le bloc ``||basic: effacer l'écran||`` sous le bloc ``||basic: pause (ms)||``.

```blocks

function Message () {
    basic.showString("Bolide")
}
input.onButtonPressed(Button.A, function () {
    Message()
    basic.pause(1000)
    basic.clearScreen()
})

```

## Étape 8

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

tinkertanker/pxt-continuous-servo

```
