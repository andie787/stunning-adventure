## What is the difference between the `push`, `pull`, and `fetch` Git commands?

When you share and update projects using Git, you’ll use some or all of the following commands:

- `git pull` - Update a remote repository with changes from your local repository.
- `git fetch` - Download changes from a remote repository to your local repository without merging them.
- `git push` - Download changes from a remote repository and then merge them into your local repository.

It’s important to understand what each command does so that you can choose the right command for your task.

The `git pull` command downloads changes from a remote repository and then merges them into your local repository. Internally, the `git pull` command uses `git fetch` followed immediately by `git merge`, or `git rebase` if you use the `--rebase` flag.

In some cases, you might want to run `git fetch` instead of `git pull` to make sure you understand the changes before merging them. The `git fetch` command downloads changes from a remote repository to your local repository without merging them. Git isolates the changes so that they don’t affect your local branch. After running `git fetch`, you can choose to run `git merge origin/<branch-name>` or `git pull` to merge the changes into your local branch. The `git merge` command has many other use cases that aren’t covered here. Learn more about `git merge`. <!--should we add a link here?-->

The `git push` command updates a remote repository with changes from your local repository. Specify the branch you want to push to with `git push <branch-name>` or set the upstream branch once on your first push using `git push --set-upstream origin <branch-name>`. It's good practice to run `git pull --rebase` before running `git push` to make sure your local branch is up-to-date with the remote branch. If there are merge conflicts, then you can resolve them locally before you push your changes to the remote branch.