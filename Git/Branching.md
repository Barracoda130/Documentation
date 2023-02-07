## What is a branch
A copy of the main codebase that can be worked on in a 'sandbox' environment. Changes made on a branch will not affect the main branch and each branch will only keep track of its own history.

## Terminology
**HEAD** - the last commit made
**master** - generally the name of the main branch
**pull request** - request to pull your code INTO the master branch

## Commands
`git branch` - shows all branches for that repo. One of them will have a `*` next to it, that indicates what the current branch you are on is.
`git checkout -b newBranch` - create a new branch. This will also switch you to the new branch.
`git checkout branchName` - switch to branch branchName.
`git diff branchName` - shows changes between the current branch and the branch branchName

## Merging
There are two ways to do this. 
### Most Common
The most common way is to push the branch up to github and then create a pull request. This is mainly used to merge your branch with the master branch once you have finished making whatever change you were doing. A pull request lets anyone look at your code and suggest changes that you should make. Once a PR has been made, if you wish to change your code, you just need to change and then commit it to github, you don't need to create a new PR every change you make. 

1. Push the branch
```shell
git push -u origin branchName
```
We need to specify the branch as it is not master anymore.
2. Once we have done this, we go to [github.com](https://www.github.com) and create a pull request from there.
3. Changes can then be viewed, commented on and updated. 
4. Once everyone is happy we merge the branch with the master branch.

Once the branch is successfully merged, normally you would delete that branch and then if you need to make additional changes, you create a new branch.
```shell
git branch -d branchName
```

### Less common
This method is mainly used to merge the master branch with your branch regularly and if you are just working on the repo solo.
1. Set the HEAD (current branch) to whatever branch you wish to have the changes saved to (ie the name of the new branch).
2. Merge them
```shell
git merge branchName
```
`branchName` is the name of the branch you want to merge the HEAD branch with.
3. Sort out any conflicts.
Git has a pretty good merging tool, however if there are direct conflicts it will ask you to sort them out. The easiest way to do this is to open up whatever editor you were using and the conflicts should have appeared along with where they came from. Then you can manually keep and remove whatever ones you want. Most good editors will have some buttons that will automatically keep all changes, remove changes from one of the branches etc.

4. If there were any conflicts that needed to be sorted out, we now need to re-commit our code after we have fixed the issues.

## Working on a branch
When you are working on a project with many other people who are all often updating the `master` branch, you will want to regularly pull `master` down and merge it with your local branch so you don't get too far behind.
1. Pull the master branch down from github
```shell
git pull origin master
```
2. Make sure you are on the current branch you are working on and NOT on master.
3. Merge your current branch with master.
```shell
git merge master
```