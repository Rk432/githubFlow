# github-workflow-basics

## Individual workflow

<img width="450" alt="image" src="https://user-images.githubusercontent.com/74586376/172043374-762e04a3-ab7c-475a-854c-f735946657b0.png">

First create a repo in github

then clone it using to local pc : (in git bash terminal in folder where you want repo)
```
git clone <repo-link>
```
create/add remote repo: (this is basically used as an alias for the repo-link)
```
git remote add <remote-name> <repo-link>

#you can check remote repos which are taken using
git remote -v

#remove existing remote repos using
git remote rm <remote-name>
```
common remote name used is <code>origin</code>

- then make changes you want in the folder created and save the files 
- then to save the changes in git for later version control we need to commit those changes
- first we add files to staging with add command
- then commit it with appropriate commit message

```
#add with file names in which changes were made/ files were added
git add <file2-name> <file2-name>

#adding all files in which changes were made / all files which were added shorthand 
git add .

#commiting files with messages for later reference
git commit -m "<commit-message>"

```
This will commit changes to local pc git

For these changes to get reflected in github cloud repo we need to push changed from local pc git to remote/cloud git
```
git push <repo-link/remote-name> <current-branch>
```
branch name can be seen from :

<img width="357" alt="image" src="https://user-images.githubusercontent.com/74586376/172044163-0cf5554e-f563-4068-ae80-a5151958005f.png">
here master is current branch.

#### Evertime you make changes then follow:
```
git add .
git commit -m "<commit message>"
git push <remote-name> <current-branch>
```




