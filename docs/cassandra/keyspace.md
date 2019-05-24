# Keyspace
* Here we'll use cqlsh for executing CQL.
* To use a case-sensitive keyspace, enclose the keyspace name in single quotes.

### Create Keyspace
    CREATE KEYSPACE MyKeySpace 
    WITH REPLICATION = {
        'class': 'SimpleStrategy',
        'replication_factor': 1    
    };    
    
### Switch Between Keyspaces
    USE MyKeySpace;
    
    
        
    
    