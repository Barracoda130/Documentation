## SSH Connection
```shell
ssh-keygen -C lcompton-burnett@hotmail.com
eval "$(ssh-agent -s)"
ssh-add github
ssh -T git@github.com
```
- This is roughly what it will look like.
- Line one generates the SSH key (Name it github).
- Line 3 then adds that SSH key to your list of keys
- and line 4 then connects to github.

## Initialising repositories
1. Initialise the repository and setup the first commit
```shell
git init
git add .
git commit -m "Initial Commit"
```
2. Now create an empty repo on github.
3. Now add the github repo to the local machine
```shell
git remote add origin GITHUB_LINK
```
Replace `GITHUB_LINK` with the link to that repo that github provides.

4. Now push to remote as described below.


# Using the repository
## Saving changes
Once you have completed a section of the code, like added a function or refactored your code. You need to **commit** it. This is the equivalent of **saving** it. To commit type:
```shell
git add .
git commit -m "MESSAGE"
```
Replace `MESSAGE` with your commit message, for example if I had just finished the file write function:
```shell
git add .
git commit -m "Finished file write function"
```

## Branching
Branches should be used when you add a new large feature to your code. For example, create a new branch for making the `ebcBlock` code, and a different branch for making the `ebcEcho` function etc.

Branches are basically copies of your code that you can change and do whatever you want to, and if it goes completely wrong, you will still have a working copy of the code that you can always go back to. For this reason, you should never write code when on the `main` branch of your project, you should only write on other branches you create and then you can join those branches with the `main` branch once you have gotten all the code working.

#### Creating a branch
```shell
git checkout -b BRANCH_NAME
```
Replace `BRANCH_NAME` with the name of your branch.

#### Moving between branches
To see which branches you have, type:
``` shell
git branch
```
and it will list all the branches you have. The branch you are currently on will show up with a `*` next to it.

To then move to one of them, type:
```shell
git checkout BRANCH_NAME
```
and again, replace `BRANCH_NAME` with the name of your branch.

#### Merging a branch
Merging is how you combine code on two different branches. Normally this would be you merging a branch you created onto the `main` branch.

1. Move to the branch you wish the merged code to end up in. So if you wanted to merge to main, move to main using `git checkout main`.
2. Merge the code by typing:
```shell
git merge BRANCH_NAME
```
3. Sometimes it will ask you which merging algorithm you want to use, select the default one.

## Pushing and Pulling
#### Pushing
Pushing and is how you actually save your code to github. When you 'commit' it only saves that locally, so in order to save it to github where you can access it from any computer, you need to 'push' it to github. 

I would recommend pushing every time you merge a branch with `main` and whenever you have got something to work that you are happy with.

To push your code type:
```shell
git push origin BRANCH_NAME
```
and replace `BRANCH_NAME` with the name of the current branch you are on.

#### Pulling
If you want to get the code you wrote and pushed from github to your machine, you need to 'pull' it.
To do that type:
```shell
git pull origin BRAHCN_NAME
```
and replace `BRANCH_NAME` with the name of the branch you want to pull. If the branch you want to pull isn't the branch you are currently on, you will need to create that branch first using the steps shown above, then move to that branch, then pull from github.





