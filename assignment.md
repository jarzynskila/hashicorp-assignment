## About git push, pull, and fetch

This document describes how the `git push`, `git pull`, and `git fetch` commands work.

### Overview 

The following table describes each command.

<table>
	<tr>
		<th>
			Command
		</th>
		<th>
			Description
		</th>
	</tr>
	<tr>
		<td>
			<code>git push</code>
		</td>
		<td>
			Sends changes from your local branch to a remote repository
		</td>
	</tr>
	<tr>
		<td>
			<code>git fetch</code>
		</td>
		<td>
			Gets changes from a remote repository into your local branch
		</td>
	</tr>
	<tr>
		<td>
			<code>git pull</code>
		</td>
		<td>
			Gets changes from a remote branch into your local branch and merges them into your local branch
		</td>
	</tr>
</table>

For more details about each command, see the following sections.

### `git push` 

`git push` does the following:

1. Checks for a remote branch that corresponds to your current local branch. 

2. Checks whether the remote branch includes any changes that are not in your local branch. If so, the command fails at this step. To resolve this issue, run `git pull` or the combination of `git fetch` and `git merge` to bring the changes into your local branch.

3. Updates the remote branch with your changes. 

Once `git push` finishes running, your local branch and the remote branch are the same.


### `git fetch` 

`git fetch` does the following:

1. Checks for a remote branch that corresponds to your current local branch. 

2. Checks for changes in the remote branch. If it finds changes, it brings them into your local branch without merging them. 

To merge the changes into your local branch, run `git merge origin/BRANCH-NAME`, where `BRANCH-NAME` is the name of the remote branch.

### `git pull` 

`git pull` does the following:

1. Runs `git fetch` to get the changes into your local branch without merging. 
2. Runs `git merge` to update your local branch. 

If you want to review the changes before merging them, you can run `git fetch` instead of `git pull`. Once you review the changes, run `git merge`. 