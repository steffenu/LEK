# Erste Normalform (1NF)

    Ein Relationstyp (Tabelle) befindet sich in der ersten Normalform (1NF), wenn die Wertebereiche der Attribute des Relationstypen atomar sind.

    ATOMAR = Einem Attribut dürfen nicht mehrere Werte aus dem definierten Gültigkeitsbereich zugeordnet sein.

(nicht atomar)
![](https://i.imgur.com/z6z5xIk.png)

(atomar)
![](https://i.imgur.com/M35oNLm.png)

# Zweite Normalform (2NF)

    Ein Relationstyp (Tabelle) befindet sich genau dann in der zweiten Normalform (2NF), wenn er sich in der ersten Normalform (1NF) befindet 
    
    und jedes Nichtschlüsselattribut von jedem Schlüsselkandidaten voll funktional abhängig ist.

  ![](https://i.imgur.com/J9vvGDb.png)

# Dritte Normalform (3NF)

    Ein Relationstyp befindet sich genau dann in der dritten Normalform (3NF), wenn er sich in der zweiten Normalform (2NF) befindet
    
    und kein Nichtschlüsselattribut transitiv von einem Kandidatenschlüssel (Primärschmlüssel) abhängt

> Note : Knr ist der Primärschlüssel..
zwischen Knr und der ortsangabe besteht keine abhängigkeit.. das müssen wir auflösen ;)

![](https://i.imgur.com/GNP0YRK.png)


# Boyce Codd Normalform (BCNF)
lies durch falls gebraucht :
https://www.datenbanken-verstehen.de/datenmodellierung/normalisierung/boyce-codd-normalform/

# Gedankliche Schritte 
  es wir d mit Begriffen wie 
  "transitiv" , "vollfunktional" , direkt , indirekt 

  um sich geworfen.

  Wenn wir diese für uns übersetzen , dann sind die Schritte Easy Bruder.


  # Übung

