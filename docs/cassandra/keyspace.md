# Keyspace

Here we'll use cqlsh for executing CQL.

#### Create Keyspace
    CREATE KEYSPACE MyKeySpace 
    WITH REPLICATION = {
        'class': 'SimpleStrategy',
        'replication_factor': 1    
    };
    
    
#### Switch Between Keyspaces
    USE MyKeySpace;
    
    
        
    
    