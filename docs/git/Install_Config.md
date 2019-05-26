## Install and Configuration

### Installing GIT
Follow the [link](https://git-scm.com/downloads) to download and install.

---

### Config
Config file locations for Mac/Unix based systems. Locations vary for windows.

###### System
    /etc/gitconfig
        
###### Global(Specifc User)
    ~/.gitconfig
    
###### Project
    Project_Folder/.git/config
    
Alternatively instead of editing the file manually, we can execute commands by passing the level where we need the change.

    E.g
    To set config at System level
        $ git config --system KEY VALUE    
    
    To set at user level 
        $ git config --global user.name "Quark Bits"
        $ git config --global user.email "myemail@example.com"
    
    To view all config,    
        $ git config --list
        
    To view specific config,   
        $ git config user.name
                

---                