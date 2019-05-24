# Table

* Keyspaces contain Tables
* Tables contain Data

## CREATE
#### Create Table
    CREATE TABLE MyTable (
        Column1 TEXT,
        Column2 INT,
        PRIMARY KEY (Column1)
    );

    
#### Create Table with PartitionKey
    CREATE TABLE MyTable (
        Column1 TEXT,
        Column2 INT,
        Column3 TEXT,
        PRIMARY KEY ((Column3),Column1)
    );


## DROP
#### Drop Table
    DROP TABLE MyTable;
 

 