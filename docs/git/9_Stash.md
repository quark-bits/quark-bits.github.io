## Stash

#### Save Stash
Stash the changes currently in working directory.    
    
    $ git stash save "some_message"
    

#### View Stash    
List the stashes

    // This will list the stashes.
    $ git stash list
    
    // From the above command, we have 'stash_ref' and can display details of stash
    $ git stash show <stash_ref>
    
    // -p option will show changes similar to diff
    $ git stash show -p  <stash_ref>
    
    
#### Apply Stash
    // removes from stash and applies to working directory.
    $ git stash pop
    
    // Applies to working directory but will not remove the stash
    $ git stash apply     
    
    Note: If we don't specify the stash_ref, then it'll apply the first one.
    
    // If we need to apply specific stash, then: 
    $ git stash pop <stash_ref>
    

#### Delete Stash
    // Delete the stash by passing the 'stash_reference'
    $ git stash drop <stash_ref>
    
    
#### Delete All (Clear) Stash
**Warning**: This will remove all stashes.
 
    $ git stash clear    

    