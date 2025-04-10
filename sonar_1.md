# Sonar 1

## @showdialog

Programme le capteur de distance.

## Étape 1

Supprime le bloc ``||basic:au démarrage||``.

## Étape 2

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:distance||``.

Ajoute le bloc ``||variables: définir distance ||`` dans le bloc ``||basic:toujours||``.


```blocks

let distance = 0
basic.forever(function () {
    distance = 0
})


```
## Étape 3

Modifie le bloc ``||variables: définir distance||``.

Remplace la valeur ``||variables: 0||`` par le bloc ``||sonar:sonde de distance||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P0,
    PingUnit.MicroSeconds
    )
})


```

## Étape 4

Modifie le bloc ``||sonar: sonde de distance|||``.

La valeur ``||sonar:P0||`` de ``||sonar:ping trig||`` demeure la même.

Remplace la valeur ``||sonar:P0||`` de ``||sonar:echo||`` pour ``||sonar:P1||``.

Remplace la valeur ``||sonar:us||`` de ``||sonar:unit||`` pour ``||sonar:cm||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
})

```


## Étape 5

Ajoute le bloc ``||logic:si alors sinon||`` sous le bloc ``||sonar: sonde de distance|||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (true) {
    	
    } else {
    	
    }
})

```

## Étape 6

Modifie le bloc ``||logic:si alors sinon||``.

Remplace la valeur ``||logic:vrai||`` par le bloc ``||logic:0 < 0||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (0 < 0) {
    	
    } else {
    	
    }
})

```

## Étape 7

Modifie le bloc ``||logic:0 < 0||``.

Remplace la valeur ``||logic:0||`` de gauche par le bloc ``||variables: distance||``.

Remplace la valeur ``||logic:0||`` de droite par la valeur ``||logic: 15||``.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (distance < 15) {
    	
    } else {
    	
    }
})

```

## Étape 8

Modifie le bloc ``||logic:si alors sinon||``.

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||logic:si alors ||``.

Choisis le ``||basic:X||`` comme icône.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (distance < 15) {
        basic.showIcon(IconNames.No)
    } else {
    	
    }
})

```

## Étape 9

Modifie le bloc ``||logic:si alors sinon||``.

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||logic:sinon||``.

Choisis le ``||basic:crochet||`` comme icône.

```blocks

let distance = 0
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (distance < 15) {
        basic.showIcon(IconNames.No)
    } else {
        basic.showIcon(IconNames.Yes)
    }
})

```

## Étape 10

Bravo ! 🎉🎉🎉

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

dstemps=github:microsoft/pxt-sonar

```

