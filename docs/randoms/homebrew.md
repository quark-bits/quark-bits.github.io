# Homebrew
Homebrew is a package manager for Mac. Macports is another package manager for Mac that is similar to Homebrew.
 
## Install
Prerequisite: homebrew needs xcode and commandline tools to be installed

    $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"


### Brew Help
    # Show Homebrew version
    $ brew --version
    
    # Print Help Information
    $ brew help
    
    # Print Help Info for a brew command
    $ brew help <sub-command>
    
    # Troubleshoot for problems
    $ brew doctor   

### Brew Update
    # Fetch latest version of homebrew and formula
    $ brew update
    
    # Show formulae with an updated version available
    $ brew outdated
    
    # Upgrade all outdated and unpinned brews
    $ brew upgrade
    
    # Upgrade only the specified brew
    $ brew upgrade <formula>

    # Prevent the specified formulae from being upgraded
    $ brew pin <formula>
    
    # Allow the specified formulae to be upgraded.
    $ brew unpin <formula>
 
  
## Must have Packages for Development.
I've indicated packages that are mostly required for a Java Developer.

###  Install Casks ##
    $ brew install cask


###  Bash Completion ##
    $ brew install bash-completion
 
###  To use OpenJDK instead of OracleJDK ##
    $ brew cask install adoptopenjdk
    (https://github.com/AdoptOpenJDK/homebrew-openjdk) [homebrew-openjdk]
 
    $ brew cask install <version>
 
###  jenv - To swich between JDK versions ##
    $ brew install jenv
    
    $ jenv add <Path_To_Java_Home>
    E.g. jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home/
    
    $ jenv versions
      system
      1.8
      1.8.0.212
      12.0
      12.0.1
    * openjdk64-1.8.0.212
      openjdk64-12.0.1
    
    // Note: version with asterix sign is the active version.
    
    $ jenv global openjdk64-12.0.1
    // This will set openjdk64-12.0.1 as Global version.
    
    
    $ cd <project_directory>
    $ jenv local openjdk64-1.8.0.212    
    // This will set openjdk64-1.8.0.212 as java version for this specific project_directory(per directory)
    
    $ jenv shell 1.8.0.212
    // Configure java for shell instance
    
    
    
  
