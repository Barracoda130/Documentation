## `clone`
Bring a repository that is hosted somewhere like Github onto your machine.
```shell
git clone repoSSHkey
```

## `add`
When you have made changes to a file/folders this tells git to track those changes.
Need to run this command before you commit.
```shell
git add fileName
# OR
git add .
```
- `git add .` will add all files in current directory to tracking.
- to be used after every problem is solved
- it stacks file changes onto a 'staging area'
- then when `git commit` is run, the whole staging area is committed as a snapshot to github

#### Undoing
To undo a stage (add) type:
```shell
git reset
# OR
git reset fileName
```
- This will unstage either all files staged or the file(s) specified.

## `commit`
Save changes made in code to Git.
When committing, it will only save to local machine. Need to use [[#`push`| git push]]
```
git commit -m "commit message"
# OR
git commit -m "Commit message title" -m "Commit message description"
# OR
git commit -am "Commit message"
```
- The `-am` flag is actually two flags, `-m` is the one we've seen before, `-a` is used to add all modified files to the commit. This will only add files that have ALREADY BEEN ADDED on a previous commit.

#### Undoing
There are 2 ways to undo a commit:
**1.** Undo the most recent commit(s)
```shell
git reset HEAD~1
# OR
git reset --hard HEAD~2
```
- `HEAD` is the most recent commit and so `HEAD~1` is the one before that, `HEAD~2` is 2 before that etc.
- This won't delete the changes made in the most recent commit, it will unstage them though and treat them as new changes that can then be staged again.
- The `--hard` flag means that instead of keeping the changes but unstaging them, it will completely delete any changes after the commit we are going back to.

**2.** Go back to a previous commit
```shell
git checkout HEAD~1
```
- This will still keep the most recent commit, however you will now be working on a different one.
- This will result in a 'detached head state'. To reattach the head, make a new commit.

For both of these methods, instead of using `HEAD~1`, you can use the `git log` command to find the hash of a certain commit and replace `HEAD~1` with that hash.

## `push`
Once you have made changes and committed them, push will upload those changes to a remote repo like Github.
```shell
git push
```

## `pull`
When there are changes on Github and you want to bring them to your local machine
```
git pull
# OR
git pull origin master
```
- `origin` is whatever you have named the repo and `master` is the branch. If you want to pull a different branch, change `master` to the branch name

## `diff`
Shows all changes between current code and the most recent commit.
```shell
git diff
```

## `log`
Shows a log of all the commits.
```shell
git log
```

## `status`
Says which branch, and if there are any uncommitted files. Also after `git add` shows branches about to be committed.
```shell
git status
```