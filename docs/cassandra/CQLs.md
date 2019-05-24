# CQLs
Syntax are very similar to Relational.

###INSERT
    
    INSERT INTO MyTable(Column1, Column2, Column3)
    VALUES ('Value1','Value2','Value3');


In the below CQL, we are inserting uuid for id.
    
    INSERT INTO MyTable(id, Column2, Column3)
    VALUES (uuid(),'Value2','Value3');

<br/>

###SELECT

    SELECT * FROM MyTable;
    
    SELECT Column1,Column2 FROM MyTable;
         
   

###SELECT
    
    TRUNCATE MyTable;
    
    
