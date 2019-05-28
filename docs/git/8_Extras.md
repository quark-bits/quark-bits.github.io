## Extras
### GIT Autocompletion
This helps while using GIT commands in commandline.
 
    1. Download the file 
        $ curl -OL https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash
    2. Rename file  
            $ mv git-completion.bash .git-completion.bash
    3. Copy to USER_HOME. 
    4. Edit ~/.bash_profile and include below lines
            if [ -f ~/.git-completion.bash ]; then
                source ~/.git-completion.bash
            fi


### Tracking Empty Directories
* By default, Git tracks only files and folders that leads to the files. 
* If we have empty directory in the project, it doesn't get tracked.
* To track directory, we can create an empty file in the directory that we wish to track. As a convention, the file 
is named as `.gitkeep` (opposite to .gitignore naming).

         
### Aliases for common Git commands
**Note**: If we are newbie to Git, better to stick with actual Git commands. 

* This will be more helpful while using Git Commands that require multiple arguments to be passed. 
* Similar to any git config, we can setup alias in System,Global,Project level. Here we consider Global(user) level.

        E.g. 
        // For Git status, we can use alias short cut 'st'.
        $ git config --global alias.st "status"    
        // Usage. Now instead of "git status", we can use "git st" command.
        $ git st
        
        // For Viewing Git log in Graphical representation.
        $ git config --global alias.logs "log --graph --decorate --oneline --abbrev-commit --all"
        // Usage.
        $ git logs
    


### Include Git Branch Name in command prompt.
When we are in command Line inside a GIT managed directory, then we can show the Branch name in the command prompt.

    1. Download the file 
        $ curl -OL https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
    2. Rename file  
            $ mv git-prompt.sh .git-prompt.sh
    3. Copy to USER_HOME. 
    4. Edit ~/.bash_profile and include below lines
            if [ -f ~/.git-prompt.sh ]; then
                source ~/.git-prompt.sh
            fi
    5. Here we can make use of Prompt variable(PS1) in Unix/Mac. 
            $ export PS1='$PWD $(__git_ps1 "[%s]") $ '            
                > PS1: Prompt Variable to which we are setting values                
                > $PWD: Current directory with full path name
                > __git_ps1: Git Prompt variable that we set with branch name when we are inside the Git directory. Outside of the Git directory this will be empty.
                > %s: is the current branch name that gets passed.
                > []:  We can use any brackets. I've used square bracket.
                
                E.g When we are in git directory with current branch "myAnotherNewBranch",  The command line prompt will be displayed as: 
                    /path/to/git/project [myAnotherNewBranch]$                          
                


