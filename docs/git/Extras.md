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
##         
### Tracking Empty Directories
* By default, Git tracks only files and folders that leads to the files. 
* If we have empty directory in the project, it doesn't get tracked.
* To track directory, we can create an empty file in the directory that we wish to track. As a convention, the file 
is named as `.gitkeep` (opposite to .gitignore naming).

##         
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
    

