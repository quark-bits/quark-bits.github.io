## Branches

#### Show Branches
    // Shows list of branches we have in Local Machine        
    $ git branch
    * master         
    
    // * next to the branch name indicates the current branch
    // We can check where HEAD points to with belo command.                
    $  cat .git/HEAD
      ref: refs/heads/master
            
#### Create Branch
    // Create New Branch.
    $ git branch myNewBranch
    
    // This just creates branch, but doesn't switch to new branch.
    // HEAD still points to master branch.
                          

#### Switch Branch        
    // Switch
    $ git checkout myNewBranch
             
    $  cat .git/HEAD
      ref: refs/heads/myNewBranch
                              
#### Create and Switch Branch at same time
    $ git checkout -b myAnotherNewBranch
    // This creates and switches to "myAnotherNewBranch"
        

#### Comparing Branches
    // $ git diff <Branch_1>..<Branch_2>
       $ git diff master..myNewBranch
       
           
- ##### Finding all other branches that are completely merged into current branch.                          
      $ git branch --merged        
        
        E.g
        1. Show current Branch. * indicates current branch.        
         $ git branch
          master
          * myAnotherNewBranch
          myNewBranch  
                          
        2. Lists other branches that are completely merged into current branch.
            git branch --merged
            master
            * myAnotherNewBranch
            myNewBranch                 
            
            // Here, 'master' & 'myNewBranch' are completely merged in 'myAnotherNewBranch'.
            
    Here, GIT goes back the ancestor chain(commit_revisions) of current branch and checks if Tip(HEAD) of other branches
    matches any of these commit_revisions.     
            

#### Renaming Branches
    // -m or --move
    $ git branch -m old_branch_name new_branch_name                                                                           
    

#### Deleting Branches
    // -d or --delete
    $ git branch -d branch_name_to_delete
            

- Git has checks in-place prior to delete.
    * We cannot delete the branch in which we currently on. So we need to switch to a different branch and then delete.
    * We cannot delete the branch which is not fully merged. If we still need to delete, then we use -D argument. 
        *  $ git branch -D branch_name_to_delete


#### Merge Branches            
        
    // To merge Branch mybranch_1 into Branch mybranch_2, first we checkout Branch mybranch_2.
    // mybranch_2 is the receiving branch.        
    $ git checkout mybranch_2 
    
    // Now mybranch_2 will be the current branch.
    $ git merge mybranch_1
    
- ##### Fast-Forward:            
        Let's say we've Master Branch as indicated below with Commit Revisions.
        
        master                         HEAD
                                        ↓ 
        8482xc - 938xol - odli223 - 31093xe  
    
        1. Now Let's create a new branch "feature_new".
            $ git checkout -b feature_new
    
        
        2. Assume we've made changes to "feature_new" and made two commits. There are no changes made to master branch.
             
            
        master                        HEAD
                                        ↓ 
        8482xc - 938xol - odli223 - 31093xe  
                                         \
                                          \
                        feature_new    7828xws  - 234uxk1
                        
        3. Now when we merge "feature_new" into master, since there are no new merges in master since the version from which "feature_new" was branched out, 
        Git will Fast-Forward i.e there will be no additional commits(commit revisions) during/due to merge.
        
        So after merge, it'll be
        
        master                                              HEAD
                                                              ↓ 
        8482xc - 938xol - odli223 - 31093xe - 7828xws  - 234uxk1
                
            - No Fast-Forward: Incase we need to force Git to create a merge commit_revision anyways during Fast-Forward, then 
                        
                    $  git merge --no-ff mybranch_1
                    
                    
                        
                    master                                                      HEAD
                                                                                 ↓ 
                    8482xc - 938xol - odli223 - 31093xe - 7828xws  - 234uxk1  - 90x9k11               
    
            - Fast-Forward Only: Incase we want Git to merge only when there is Fast-Forward and to abort otherwise,
            
                    $  git merge --ff-only mybranch_1


- ##### Merge Conflicts:
    - ###### Abort Merge         
            $ git merge --abort   

    - ###### Resolve Conflict manually
            // Git will mark the files with code block that has conflicts. We need to manually make changes and resolve conflict.

            // Other option is to use mergetool to ease the resolving of merge conflicts.
            // Below command displays the tools that are avaiable to be used.            
            $ git mergetool