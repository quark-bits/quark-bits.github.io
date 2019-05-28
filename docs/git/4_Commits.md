## Commits

### Tree Listing
    $ git ls-tree <tree-ish>  // tree-ish is reference to Tree. This can be HEAD, Commit Version..
    
    E.g
    $ git ls-tree HEAD
    $ git ls-tree HEAD some_directory
    
    
### Commit Logs
#### View Commit Logs
* Show OneLine Logs
    
        // Show One Line Log information
        $ git log --oneline                

* Limit number of commits to show

        //Show last 5 commits
        $ git log --oneline -5
        
* Limit number of commits based on time

        //Show commits since a date
        $ git log --since="2019-05-26"
        // we can use until, before, after for dates                        
        
* Limit commits based on author
    
        //Show commits for author GSK
        $ git log --author="GSK"


* List everything that has happened on a file since a particular commit

        $ git log <Commit_Revision>.. filename.ext                
        
        
* List changes that has happened along with log
    
        $ git log -p
        // This will show diff in what changed in each commit.         
        
        
* List statistics/Summary of the commit logs

        $ git log --stat --summary        
        
        
* List Commit Logs in Graph display
        
        $ git log --graph --all
        // This will show the branching incase of multiple branches in a nice Graphical display.        
        
        
* View Git Commit Info

        $ git show <Tree-ish>        
                

#### Compare Commits

* Show difference between working directory and that point in time when commit was made.  

        $ git diff <Commit_Revision>


* Show difference between working directory and that point in time when commit was made for **a specific file.**  

        $ git diff <Commit_Revision> filename.ext
        
        
* Show difference between two different commits.

        $ git diff <Commit_Revision_1>..<Commit_Revision_2>
                        

* Show difference between two different commits for **a specific file.**.

        $ git diff <Commit_Revision_1>..<Commit_Revision_2> filename.ext
        

* To Ignore whitespaces/changes due to whitespaces
        
        $ git diff -w  <Commit_Revision>
        
        $ git diff -b  <Commit_Revision>
        
        -b 
        --ignore-space-change 
        Ignore changes in amount of whitespace. This ignores whitespace at line end, and considers all other sequences of one or more whitespace characters to be equivalent.
        
        -w 
        --ignore-all-space 
        Ignore whitespace when comparing lines. This ignores differences even if one line has whitespace where the other line has none.
                       
        