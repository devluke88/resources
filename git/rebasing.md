# Rebasing

Rebasing means changing the old base of the branch to a new one built on the top of the master/main branch. It also allows you to change individual commits.

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `git rebase [new-base]` | Change the old base to the \[new-base\] \(include all changes that were done in the main branch or a commit ID\). It is similar to merge, but this will include all commits history. |
| 2 | `git rebase -i main` | Option `-i` means interactive. This lets you edit the list of commits that are about to be rebased. You can condense two commits in one - use `squash` or `edit` to make some amendments - this basically pauses the rebase. For example, you can add your change to staging and next to include it in your `edit` commit use `git commit --amend` to replace the commit message.  |
|  3 | `git rebase --continue` | This is the last step to do after the command above. |
| 4 | `git rebase --abort` | When you are in the middle of rebasing and you are not sure if you should continue, you can use `--abort` flag to discard changes and start from scratch. |



