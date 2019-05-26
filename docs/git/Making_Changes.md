## Making Changes to File

##### Adding Files
    Add all files 
    $ git add .
    
    Add specific file
    $ git add /folder_name/filename.ext
    
##### Editing Files    
We edit the file and use same commands as Adding Files. 


##### View Changes 
    For working file
    $ git diff

    For staged file
    $ git diff --staged

    View change in different color side by side
    $ git diff --color-words                
                   
##### Deleting Files
    Option-1: Manually Delete the file from the location.
        $ rm /folder_name/filename.ext
        $ git add /folder_name/filename.ext
        $ git commit -m "commit_message"
        
    Option-2: Using git command to remove file
        $ git rm /folder_name/filename.ext
        $ git commit -m "commit_message"
                
            
##### Undoing Changes
* Undo changes to working directory changes. (changes that are not staged/commited)

        $ git checkout -- /folder_name/filename.ext       
                
        Note: -- is used because git checkout is also used to checkout a branch. So if the file/folder name that we
        intend to undo change matches to some branch name in repo, then instead of undo it'll checkout the branch.
                    
* Undo changes to staged files.(changes that are staged but not commited)
    
         $ git reset HEAD /folder_name/filename.ext    
        Note: Now we've unstaged the file. The changes are now part of working directory changes (unstaged changes).
                
* Undo commits made to repo.

        Note: GIT uses previous commit revision(hash) + current changes to create new commit revision(hash). So we cannot 
        modify older/earlier commits except for the last one(Header Pointer).
        
        We follow regular steps to edit file and stage the file. only the commit command will change.         
        $ git commit --amend -m "commit message"

        // This can also be used to modify "commit_message" of recent commit.
        
* Retreiving older version file

        // Use git log to obtain the older commit revision of the file 
        $ git log                
        commit 9a93b0806a3fcad437ae36bcd902db7a4d1fa96b
        Author: Name<Email>
        Date:   Sat May 25 05:08:19 2019 -0700
        
            test.txt

        $ git checkout 9a93b0806a3fca -- test.txt
        // Note: We don't need to put in entire revision number, first 10 or so chars should be enough.
        

* Reverting commit

        // Revert all changes made during a commit using commit revision number.
        $ git revert 9a93b0806a3fca         
             