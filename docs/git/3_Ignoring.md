## Ignoring the Files

What to Ignore?
* Compiled Source Code.
* Packages and Compressed files. E.g zip
* Logs and Databases.
* OS generated files. 
* User-Uploaded assets.(images, videos, pdf)

###### Project Level Ignore 
    // Applies to specific GIT Project under which the file is created
    $ <project_folder>/.gitignore

###### Global Level Ignore 
    //Applies to all GIT projects
    $ git config --global core.excludes_file <PATH_TO_GIT_IGNORE_FILE>    
    
    We can verify this from ~/.gitconfig file. It'll now include "excludesfile" property.                  
                
###### Ignore Tracked Files            
One use-case could be, we want to keep Default_Configuration file committed into Repo and 
make changes to the file based on Local System settings which we do not want to track.

    $ git rm --cached /folder_name/filename.ext
    
* This tells Git to remove this file from staging index but not from Repo or Working Directory.
* with **`git status`**, command we can see this file status is shown as deleted but the file exists in the location. 
                    
        
    
        