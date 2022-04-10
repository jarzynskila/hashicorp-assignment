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
			Sends changes from a local branch to a remote repository
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
			Gets changes from a remote branch into your local branch and merges them into a local branch
		</td>
	</tr>
</table>

For more details about each command, see the following sections.

### `git push` 

`git push` checks to see if there is a remote branch that corresponds to your current local branch. If so, it takes your changes from your local branch and pushes them to the remote branch. This is how you share code with a remote repository, you can think of it as "make the remote branch resemble my local branch". This fails if the remote branch has commits that are not in your local branch. When this happens, you must synchronize your local branch with the remote branch with git pull or git fetch and git merge.

### `git fetch` 

`git fetch` checks to see if there is a remote branch that corresponds to your current local branch. If so, it looks for changes in the remote branch, and pulls them into the local branch. It does not change your local branch. To do that, you'll need to do `git merge origin/main` (for the "main" branch) to merge those changes into your local branch - probably also called "main".

### `git pull` 

`git pull` does a `git fetch` followed immediately by `git merge`. Some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.