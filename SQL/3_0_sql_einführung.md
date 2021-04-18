
# SELECT

    SELECT c1, c2 FROM t;
    = Spalten abfragen

#
    SELECT * FROM t;
    = Alle Zeilen und Spalten abfragen
#
    SELECT DISTINCT c1 FROM t
    = Mit DISTINCT filtert man doppelte werte raus


# CREATE
    CREATE DATABASE databasename;

#

    CREATE TABLE table_name (
        column1 datatype,
        column2 datatype,
        column3 datatype,
    ....
    );

    CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);

  

# DROP
    DROP DATABASE databasename;

    DROP TABLE table_name;

# INSERT 

    INSERT INTO table_name (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...);

    If you are adding values for all the columns of the table ->

    INSERT INTO table_name
    VALUES (value1, value2, value3, ...);

# UPDATE
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE condition;

# DELETE
    DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';

    delete all rows in a table -->

    DELETE FROM table_name;

# ALTER
    ALTER TABLE table_name
    ADD column_name datatype;

    ALTER TABLE table_name
    DROP COLUMN column_name;

    ALTER TABLE table_name
    ALTER COLUMN column_name datatype;


#
# 
#

# START TRANSACTION
# COMMIT
# ROLLBACK



