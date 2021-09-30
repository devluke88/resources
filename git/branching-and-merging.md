# Branching and Merging

Branches allow you to do the following:

* create new features
* apply hotfixes, quick changes
* record the history of the project

| \# | Command | Description |
| :--- | :--- | :--- |
| 1 | `git branch` | Show the list of all branches. |
| 2 | `git branch [branch_name]` | Create a new branch using the current working directory as its base. |
| 3 | `git checkout [branch_name]` | Switch the branch. |
| 4 | `git checkout -b [branch_name]` | Create and switch to a new branch. |
| 5 | `git merge [branch_name]` | Merge \[branch\_name\] into the current checked-out. |
| 6 | `git merge --no-ff [branch_name]` | Force a merge commit even if git could do a fast-forward merge. |
| 7 | `git branch -d [branch_name]` | Delete a branch \(only for merged changes\). |
| 8  | `git branch -D [branch_name]` | Force to delete a branch even if contains unmerged changes. |
| 9  | `git rm [file]` | Remove a file from the working directory and stop tracking it. |



