# Group workflow
follow [Optimal Workflow](#optimal-workflow) 

## Explaination and problems from following individual workflow
<img width="575" alt="image" src="https://user-images.githubusercontent.com/74586376/172044395-3f6d586d-f8aa-4b27-965a-048860ceab97.png">

- First we need to fork from organization / team leaders repo with fork button on top right of repo.
- This will create a repo in your github profile which is linked with original repo.
- Then you can clone your forked repo to local pc
- then you can work add --> commit --> push to ur forked repo
- this will show changes in your forked repo but not in Org repo 
- to add to Org repo you need to send 'Pull Request' and then Org will accept it.

To send <code>Pull Request</code>

<img width="926" alt="image" src="https://user-images.githubusercontent.com/74586376/172044596-baac1c31-7a6a-4ed7-997c-018c1763643c.png">
tap green button you can see changed files , and you can give title and description to pull request.

### Problems with this flow
But this flow always doesnt work because multiple people are working on the project.
for example:
- 5 people fork at same time 
- employee2 works on it on local pc pushes changes to his/her forked repo and sends pull req to org and it gets accepted
- but now your forked repo (employee1) is behind the organization as it doesnt have the changes made by employee2
- if you (employee1) work on old repo and push changed to you forked repo and send pull request
- some changes might conflict with employee2's changes and this will throw a merge conflict error
- this needs to be resolved manually

### NOTE on PULL PUSH
- push is always easier than pull as push only has to retain the files it has made changes to.
- pull however has to compare changes and if github compare-strategies work it merges them , else it throws merge conflicts to be resolved
- hence when youu 'PULL from upstream' or 'send PULL request' it can throw merge conflicts
- but  resolving conflicts at local level is better than sending conflicts to organization to resolve hence we follow the below workflow.

## Optimal workflow
<img width="950" alt="image" src="https://user-images.githubusercontent.com/74586376/172187728-8feee95b-3ae3-45f6-8068-4e4b1deca215.png">

- first fork --> clone
- then make changes --> add --> commit
- fetch from organization
- merge that to local repo 
- if any merge conflicts ( resolve in speccific files --> add --> commit ) else ( just continue )
- push from local pc repo to forked repo
- send pull request to organization

setting up remotes: commonly we use <code>upstream</code> as organization remote and <code>origin</code> as forked repo remote
```
#setting remote for org repo
git remote add upstream <org-repo-link>

#setting remote for forked repo
git remote add origin <forked-repo-link>
```
Follow commands as follows after every change
```
git add .
git commit -m "<commit-message>"

#fetching and merging
git fetch upstream
git merge upstream/<current-branch>
```

<strong>NOTE:</strong> Github tries to merge files with different strategies but if the files have changes too conflicting and github can't decide it throws merge conflict error. if it can compare and merge it then it just fast-tracks and merges and you dont need to resolve anything.

if merge conflicts - example :

- org repo: 

<img width="275" alt="image" src="https://user-images.githubusercontent.com/74586376/172184294-29513ea2-b99c-4a13-9a2a-fa83bc6976ec.png">

- your file before merge command: 

<img width="275" alt="image" src="https://user-images.githubusercontent.com/74586376/172184491-9e62e6f0-64d7-43c5-b1ad-258c632ee8dd.png">

- after merge command you can see this in your files where ever conflicts occured and you need to resolve it:

<img width="275" alt="image" src="https://user-images.githubusercontent.com/74586376/172184167-83284c54-48d9-40ec-8d94-1816337ebc4e.png">

- from the colored lines in above image keep whatever changes you want (dont forget to remove the HEAD , upstream , === lines showed to indicate conflicts)

<img width="275" alt="image" src="https://user-images.githubusercontent.com/74586376/172185506-59d424e3-60be-4d90-b3fa-85412893f62a.png">

- then <code>add commit</code> 

Then follow commands

```
git push origin main

send pull request to organization repo from github
```



