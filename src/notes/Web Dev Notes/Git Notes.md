To add a remote gitHub repository type `git remote add origin <link to gitHub repository>`

If there is a need to do a git pull but getting the error `refusing to merge unrelated histories` then run the following command `git pull origin master --allow-unrelated-histories`







`git init` - initializes a local git repository

`git status` - shows the status of the git repository

`git add <filename>` - adds that file to the git repository

`git add .` - adds all of the changed files to the git repository

`git commit -m "<message>"` - adds a message to the commit that was done

`git remote add origin <website address for the project on github>` - connects local git repository to github

`git push - u origin master` - pushes the changes out to github

 

\* Need to create a new branch- only known working code should be put on the master branch

`git checkout -b <name of new branch>` - creates a new branch with the given name

Set user name `git config --global user.name "<name>"` 

Set user email `git config --global user.email "<email>"` 

Set GitHub username `git config --global user.username "<github username>"` 

 

**<u>How to create a git repository</u>** 

1. Make a new folder `mkdir hello-world` 
2. Go into that folder `cd hello-world`
3. Create a new git instance for the project `git init` 

 

To check that the folder is a git repository type `git status` 

- Git-status is also used to see if there has been any changes to the repository 

 

To add files that you would like to commit type `git add readme.txt` or `git commit .` 

To commit the changes to the repository type `git commit -m "<commit message>"` 

To see the changes from the last commit type `git diff` 

 

**<u>How to create a remote GitHub repository</u>** 

1. Log into GitHub 
2. Click on the Create Repository button 
3. Enter the name and the description  
4. Make sure that the repository is set to public 
5. Check the initialize README if you don't already have one created 
6. Set the .gitignore and license to the desired options  
   - .gitignore are the files that you don't want to be made public like files with passwords 
7. Click Create Repository button 

 

To connect the local repository to the remote repository type

`git remote add origin <URL FROM GITHUB>` 

To push all of the local files to the remote repository type `git push -u origin master` 

You will most likely be asked to type in you GitHub username and password 

 

Add remote connections `git remote add <REMOTENAME> <URL> `

Set a URL to a remote`git remote set-url <REMOTENAME> <URL>`  

Pull in changes `git pull <REMOTENAME> <BRANCHNAME>`  

View remote connections `git remote -v`  

Push changes `git push <REMOTENAME> <BRANCH> ` 

To create a branch type `git branch <branch name>` 

To go into a branch type `git checkout <branch name>` 

Create and switch to a branch in one line `git checkout -b <BRANCHNAME>` 

Create a new branch `git branch <BRANCHNAME>` 

Move onto a branch `git checkout <BRANCHNAME>` 

List the branches `git branch` 

Rename a branch you're currently on `git branch -m <NEWBRANCHNAME>` 

Verify what branch you're working on `git status` 

 



**<u>To fork a repository</u>** 

1. go to the repository that you would like to fork  
2. click on the fork button 

When the animation is done, the fork will be on your repository listing 

- A fork of repository is taking a copy of someone else's repository and putting on yours 

 

**<u>How to clone a fork locally</u>** 

1. Change the directory to one that doesn't have a git repository 
2. Clone the repository by typing `git clone <URL FROM GITHUB>` 
   - This will create a new folder for the clone 
3. Change the directory to the newly created folder 

A clone of a repository is a copy of a repository that is saved onto your local machine

 

To connect to original repository type `git remote add upstream <URL>` 

Upstream can be changed to whatever you would like to call it, upstream is the common name that is used 

 



 

