## Content

### What is the difference between push, pull, and fetch?

- `git push` - sent changes from a local branch to a remote repository
- `git fetch` - get changes from a remote repository into your tracking branch
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

`git push` checks to see whether or not there is a tracking branch for a remote repository connected to our current branch. If so, our changes are taken from our branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.`git fetch` checks to see if there is a tracking branch for our current branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/main` (for the "main" branch) to merge those changes into your branch - probably also called "main".`git pull` does a `git fetch` followed immediately by `git merge`. Some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.