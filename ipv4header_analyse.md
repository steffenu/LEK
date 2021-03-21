![](https://i.imgur.com/aTHye8w.png)

1 Ziffer sind 1  =4bit (4)

2 Ziffern = 1 byte = 8 bit (45)

    somit kann man abzählen
    welche ziffern den jeweiligen
    information entsprechen
    (aufgabenheader ist ggf misleading weil ttl nicht als 8 bit gezeigt wird .. ihk trap)

![](https://i.imgur.com/rC8qsA5.png)

    dann einfach die hex werte in binär umwandeln

![](https://i.imgur.com/aPgB0sy.png)

Quell ip

c3 0a 24 bc

Ziel ip

c0 a8 01 0a

länge datenpaket

05 ac

Rechnung für Quell IP :

## Methode 1
Hex zu Binär zu Dezimal
= leichter aber länger ;)

![hex to binary to decimal](https://i.imgur.com/S8me2eT.png)


c = 1100

0 = 0000 

  1100 0000 = 128 + 64 = __192__

a = 1010

8 = 1000

  1010 1000 = 128 + 32 + 4 = __168__

0 = 0000

1 = 0001

  0000 0001 = __1__

0 = 0000

a = 1010

  0000 1010 = 2 + 8 = __10__

__= 192.168.1.10__

---

## Methode 2
Hex zu Dezimal direkt
Schwierig ggf ohne Taschenrechner ;)

0-9..
a = 10
b = 11
c = 12
d = 13
e = 14
f = 15

c0 = 12*16^1 + 0 * 16^0 = __192__

a8 = 10*16^1 + 8 *16^0 = __168__

01 = 0*16^1 + 1*16^0 = __1__

11 = 1*16^1 + 1 * 16^0 = __17__

---

## *Grüsse gehen raus an deinen Erfolg ! ;)*