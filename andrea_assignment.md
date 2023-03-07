## What is the difference between the push, pull, and fetch Git commands?

When you share and update projects using Git, you’ll use some or all of the following commands:

- `git fetch` - Download changes from a remote repository to your local repository without merging them.
- `git pull` - Update a remote repository with changes from your local repository.
- `git push` - Download changes from a remote repository and then merge them into your local repository.

It’s important to understand what each command does so that you can choose the right command for the right task.

`git pull` simply does a `git fetch` followed immediately by `git merge`. This is often what we desire to do, but some people prefer to use git fetch followed by git merge to make sure they understand the changes they are merging into their branch before the merge happens.

`git fetch` again takes your current branch, and checks to see if there is a tracking branch. If so, it looks for changes in the remote branch, and pulls them into the tracking branch. It does not change your local branch. To do that, you'll need to do `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".

`git push` takes your current branch, and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, your changes are taken from your branch and pushed to the remote branch. This is how code is shared with a remote repository, you can think of it as "make the remote branch resemble my local branch". This will fail if the remote branch has diverged from your local branch: if not all the commits in the remote branch are in your local branch. When this happens, your local branch needs to be synchronized with the remote branch with git pull or git fetch and git merge.