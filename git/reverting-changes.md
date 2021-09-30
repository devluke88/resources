# Reverting Changes

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `git checkout [commit-id]` | This command allows you to view the contents of a previous snapshot. |
| 2 | `git revert [commit-id]` | Undo the existing commit by applying a new revert commit. Before this is applied it will show you the commit message which you can edit. |
| 3 | `git reset` | Unstage all tracked files. |
| 4 | `git reset [file]` | It allows you to undo the tracked file. It reverts `git add [file]` |
| 5 | `git reset --hard` | Removes all changes from the staging area. |
| 6 | `git reset --hard HEAD~1` | It will reset your branch to the previous commit, it will completely delete the commit and remove files from untracked files. |
| 7  | `git clean -f` | Remove untracked files. |
| 8 | `git reset --hard / git clean -f` | Permanently undo uncommitted changes. |



