Zusammenfassung Datenbanken

    Hauptthemen 
        • Einführung in SQL
        • Normalisierung
        • Entity-Relationship-Diagramme
        • Weitere SQl-Befehle

Einführung in SQL

    • CREATE
    • ALTER
    • DROP
    • INSERT 
    • UPDATE
    • DELETE

    • SELECT
    • START TRANSACTION

    • COMMIT
    • ROLLBACK
#
    Datentypen (erster Teil)
        • INTEGER
        • VARCHAR
        • CHAR
        • DECIMAL
        • DOUBLE
        
    Datentypen (zweiter Teil)
        • DATE
        • TIME
        • DATETIME
        • TIMESTAMP
#
    DISTINCT – Operator
    PRIMARY KEY
    WHERE-Klausel
        • LIKE
        • =
        • Wildcards (% _)
        • BETWEEN
        • IN
#
CROSS JOIN

    Logische Operatoren
        • AND
        • OR
        • NOT
        • XOR
#        
    Ganzzahloperatoren
        • DIV
        • MOD
#
    Gruppenfunktionen
        • MIN
        • MAX
        • COUNT
        • SUM
        • AVG
#
    Gruppierung, Sortierung
        • GROUP BY
        • HAVING
        • ORDER BY
        • Andere Formulierung mit Korreliertem Subselect
#
    Normalisierung
    1.Normalform
    2.Normalform
    3.Normalform
    BCNF(Boyce-Codd)

#
    Implementation der Normalisierung
        • FOREIGN KEY
        • PRIMARY KEY
        • Referentielle Integrität
        • Grundlagen für Beziehungen
        • INNER JOIN
#
        OUTER JOINs
        LEFT OUTER
        RIGHT OUTER
        FULL OUTER ~ UNION / UNION ALL


Umgang mit NULL

    • NULL wird von OUTER JOINs generiert
    • Ersetzen mit  IFNULL / ISNULL / NVL
    • COALESCE
    • IS Operator zum Vergleich

Krähenfuß-Notation (Martin)

Optional

    • UNION
    • UNION ALL
    • MINUS
    • INTERSECT

    • ALL 
    • ANY
    • EXISTS