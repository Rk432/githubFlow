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

to avoid this we follow a simple rule <code> always PULL before PUSH </code>

## Optimal workflow
<img width="950" alt="image" src="https://user-images.githubusercontent.com/74586376/172044858-f64501bb-caa9-406c-9176-093f4c279b1b.png">

- first fork --> clone
- then make changes --> add --> commit
- pull from organization to forked repo
- pull from forked repo to local pc repo
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
git pull upstream origin
git pull origin <current-branch>
git push origin <current branch>

then send PULL REQUEST to org from github forked repo.
```
