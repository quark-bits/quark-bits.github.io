## Remotes

### Remote Repository

##### Display Remote Repository
    $ git remote
    
    // To display verbose details
    $ git remote -v
    
    // Remote Repo info is saved in config
    $ cat .git/config 

##### Adding Remote Repository
    $ git remote add origin https://git_url/repo.git
    // origin is alias name. we could call anything, but convention its called origin.     
        
    
##### Removing Remote Repository
    // remove by passing alias name    
    $ git remote rm origin 

    
##### Cloning an existing Repository     
    $ git clone https://git_url/repo.git
    
   - By default, it creates folder "repo" and clones from remote.
   - If we need different name, we can use `git clone https://git_url/repo.git repo_new`. Now it creates "repo_new" folder and clones from remote.
   - The default branch that is configured in Git Rep is checked-out and tracked by default when we clone.
                 


### Remote Branches
    
##### Display Remote Branches

    // Below command to display Local branches
    $  git branch
        
    // with -r argument, display only remote branches
    // Here remote branches are not directly displayed from Remote repo, but instead that are already synced.
    // By using "git fetch" we can sync with repository.
    $ git branch -r
    
    // with -a argument, Local and Remote branches are  displayed
    $ git branch -a
        

##### Create Remote Branch
    // -u will track the local branch with remote
    $ git push -u origin <BRANCH_NAME>



##### Tracking Remote Branch

   1. Manually enter in .git/config

            We can set the property "remote" = alias_name of the remote branch.
        
            [remote "origin"]
                        url = https://git_url/repo.git                        
                        ...     
                      
            [branch "branch_to_track"]
                remote = origin   // we add this mapping      
                ...     
                            
            E.g. Here, "origin" is the alias of the remote branch.                 
   
   2. Command Line Git Config
            
           $ git config branch.<branch_to_track> refs/head/<Branch_With_Which_We_Want_To_Track>
   

##### Fetch Changes from Remote Repository
If we need to sync branch with remote repository, we use fetch command.
    
    $ git fetch
    
    
##### Pull from Repository
    $ git pull = git fetch + git merge.
    
    
##### Checkout Remote Branch
    $ git checkout -b Branch_Name origin/Remote_Branch_Name
    // Here origin is the alias for the remote_branch 

##### Deleting Remote Branch
    $ git push origin :RemoteBranchName
    
    //Note: Actual usage is git push origin MyLocalBranch:MyRemoteBranch, this tells push LocalBranch "MyLocalBranch" to RemoteBranch "MyRemoteBranch".
    // But incase of delete, since we do not pass "LocalBranch" prior to :, it tells push nothing to RemoteBranch. So it deletes in remote.
    
    Alternatively, the more intutive command is 
    $ git push origin --delete MyRemoteBranch
    
                             