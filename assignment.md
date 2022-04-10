## About git push, pull, and fetch

### Overview 

- `git push` - sends changes from a local branch to a remote repository
- `git fetch` - gets changes from a remote repository into your tracking branch
- `git pull` - gets changes from a remote branch into your tracking branch and merges them into a local branch

### `git push` 

`git push` checks to see whether or not there is a tracking branch for a remote repository connected to your current branch. If so, it takes your changes from your branch and pushes them to the remote branch. This is how you share code with a remote repository, you can think of it as "make the remote branch resemble my local branch". This fails if the remote branch has commits that are not in your local branch. When this happens, you must synchronize your local branch with the remote branch with git pull or git fetch and git merge.

### `git fetch` 

`git fetch` checks to see if there is a tracking branch for your current branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/main` (for the "main" branch) to merge those changes into your branch - probably also called "main".

### `git pull` 

`git pull` does a `git fetch` followed immediately by `git merge`. Some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.