# Sonde 2

## @showdialog

Programme le capteur de distance et les moteurs.

## Étape 1

Ajoute le bloc ``||basic: pause (ms)||`` dans le bloc ``||basic: au démarrage)||``.

Remplace la valeur ``||basic: 100||`` par ``||basic: 3000||``.

```blocks

basic.pause(3000)

```

## Étape 2

Ajoute le bloc ``||basic: montrer l'icône||`` sous le bloc ``||basic: pause (ms)||``.

Sélectionne le crochet comme icône.

```blocks

basic.pause(3000)
basic.showIcon(IconNames.Yes)

```

## Étape 3

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Avancer||``.

```blocks

function Avancer () {

}

```

## Étape 4

Ajoute le bloc ``||continuousservo:spin one way||`` (trad. : tourner dans un sens) dans le bloc ``||functions:Avancer||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P14||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:25||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
}

```

## Étape 5

Ajoute le bloc ``||continuousservo:spin other way||`` (trad. : tourner dans l'autre sens) sous le bloc ``||continuousservo:spin one way||``.

Remplace la valeur ``||continuousservo:P0||`` par ``||continuousservo:P13||``.

Remplace la valeur ``||continuousservo:0||`` par la valeur ``||continuousservo:25||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 25)
}

```
## Étape 6

Ajoute le bloc ``||basic:montrer LEDs||`` sous le bloc ``||continuousservo:spin one way||``.

Dessine une flèche qui pointe vers le haut.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 25)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 25)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}

```

## Étape 7

Crée une ``||functions: fonction||`` et donne-lui le nom ``||functions:Arreter||``.
```blocks

function Arreter () {
	
}

```

## Étape 8

Ajoute deux blocs ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs) dans le bloc ``||functions:Arreter||``.

Remplace les valeurs ``||continuousservo:P0||`` par ``||continuousservo:P14||`` et ``||continuousservo:P13||``.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
}

```

## Étape 9

Ajoute le bloc ``||basic:montrer l'icône||`` sous le bloc ``||continuousservo:turn off motor||`` (trad. : éteindre les moteurs).

Sélectionne ``||basic:le X||`` comme icône.

```blocks

function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}

```

## Étape 10

Crée une ``||variables: variable||`` et donne-lui le nom ``||variables:distance||``.

Ajoute le bloc ``||variables: définir distance ||`` dans le bloc ``||basic:toujours||``.


```blocks

let distance = 0
basic.forever(function () {
    distance = 0
})


```
## Étape 11

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

## Étape 12

Modifie le bloc ``||sonar:sonde de distance|||``.

La valeur ``||sonar:P0||`` pour ``||sonar:ping trig||`` demeure la même.

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


## Étape 13

Ajoute le bloc ``||logic:si alors sinon||`` sous le bloc ``||sonar:sonde de distance|||``.

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

## Étape 14

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

## Étape 15

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

## Étape 16

Modifie le bloc ``||logic:si alors sinon||``.

Ajoute le bloc ``||functions: appel Arreter||`` sous le bloc ``||logic:si alors ||``.

Ajoute le bloc ``||functions: appel Avancer||`` sous le bloc ``||logic:sinon ||``.

```blocks

function Avancer () {
    ContinuousServo.spin_one_way_with_speed(AnalogPin.P14, 23)
    ContinuousServo.spin_other_way_with_speed(AnalogPin.P13, 20)
    basic.showLeds(`
        . . # . .
        . # # # .
        # . # . #
        . . # . .
        . . # . .
        `)
}
function Arreter () {
    ContinuousServo.turn_off_motor(DigitalPin.P14)
    ContinuousServo.turn_off_motor(DigitalPin.P13)
    basic.showIcon(IconNames.No)
}
let distance = 0
basic.pause(3000)
basic.showIcon(IconNames.Yes)
basic.forever(function () {
    distance = sonar.ping(
    DigitalPin.P0,
    DigitalPin.P1,
    PingUnit.Centimeters
    )
    if (distance < 15) {
        Arreter()
    } else {
        Avancer()
    }
})

```

## Étape 17

Bravo !

Tu as terminé le tutoriel. Télécharge et teste le programme.

```package

tinkertanker/pxt-continuous-servo
dstemps=github:microsoft/pxt-sonar

```

