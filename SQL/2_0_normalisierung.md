# Die Nullte Normalform 
    ist dann gegeben, wenn alle Informationen in einer Tabelle vorhanden sind und noch unnormalisiert vorliegen.

![](https://i.imgur.com/p0kBrlT.png)


# Erste Normalform (1NF)

    Ein Relationstyp (Tabelle) befindet sich in der ersten Normalform (1NF), wenn die Wertebereiche der Attribute des Relationstypen atomar sind.

    ATOMAR = Einem Attribut dürfen nicht mehrere Werte aus dem definierten Gültigkeitsbereich zugeordnet sein.

(nicht atomar)
![](https://i.imgur.com/z6z5xIk.png)

(atomar)
![](https://i.imgur.com/M35oNLm.png)

> Alle Informationen müssen in einzelnen Spalten stehen

*Praktischer Nutzen* :

    Abfragen der Datenbank werden durch die 1NF erleichtert bzw. überhaupt erst ermöglicht, wenn die Attributwertebereiche atomar sind. So ist es beispielsweise in einem Feld, das einen ganzen Namensstring aus Titel, Vorname und Nachname enthält, schwierig bis unmöglich, nach Nachnamen zu sortieren.

# Zweite Normalform (2NF)

    Ein Relationstyp (Tabelle) befindet sich genau dann in der zweiten Normalform (2NF), wenn er sich in der ersten Normalform (1NF) befindet 
    
    und jedes Nichtschlüsselattribut von jedem Schlüsselkandidaten voll funktional abhängig ist.

  ![](https://i.imgur.com/J9vvGDb.png)

> Die 2. NF hat die Aufgabe, Teilabhängigkeiten zu eliminieren, indem sie aus diesen eigene
Relationen erstellt.

Praktischer Nutzen

    Die 2NF erzwingt wesentlich „monothematische“ Relationen im Schema: jede Relation modelliert nur einen Sachverhalt.

    Nur noch logisch/sachlich zusammengehörige Informationen finden sich in einer Relation. Dadurch fällt das Verständnis der Datenstrukturen leichter.

# Dritte Normalform (3NF)

    Ein Relationstyp befindet sich genau dann in der dritten Normalform (3NF), wenn er sich in der zweiten Normalform (2NF) befindet
    
    und kein Nichtschlüsselattribut transitiv von einem Kandidatenschlüssel (Primärschmlüssel) abhängt



> Die transitiv abhängigen Spalten werden in eine weitere Untertabelle ausgelagert, da sie nicht
direkt vom Schlüsselkandidaten abhängen, sondern nur indirekt.

![](https://i.imgur.com/Xo7mIQP.png)


# Boyce Codd Normalform (BCNF)
lies durch falls gebraucht :
https://www.datenbanken-verstehen.de/datenmodellierung/normalisierung/boyce-codd-normalform/

https://de.wikipedia.org/wiki/Normalisierung_(Datenbank)#Erste_Normalform_(1NF)




