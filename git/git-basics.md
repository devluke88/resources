# Git Basics

| #  | Command                                   | Description                                                                                                                                                                         |
| -- | ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | `git init [repo-directory]`               | Initializes a new local repository in the specified directory.                                                                                                                      |
| 2  | `git add [filename]`                      | Move untracked files to the staging area.                                                                                                                                           |
| 3  | `git add .`                               | Move all untracked files to the staging area from the current directory.                                                                                                            |
| 4  | `git add -A`                              | Add all untracked files to the staging area from the whole repo.                                                                                                                    |
| 5  | `git status`                              | Shows status of the current repository.                                                                                                                                             |
| 6  | `git commit`                              | Open commit in nano editor where you can enter a commit message.                                                                                                                    |
| 7  | `git commit -m "Commit message"`          | Commit and add a commit message.                                                                                                                                                    |
| 8  | `git commit -a -m "Commit message"`       | This command will add all modified or deleted files to the staging area (new files are not affected) and commit them at the same time. So basically we are skipping the staging are |
| 9  | `git log`                                 | It shows the list of commits.                                                                                                                                                       |
| 10 | `git log --oneline`                       | It shows the history of the commit in one line.                                                                                                                                     |
| 11 | `git log -p`                              | It shows the list of commits with diff.                                                                                                                                             |
| 12 | `git diff`                                | This will compare the working tree to the index and show you the difference.                                                                                                        |
| 13 | `git fetch && git checkout [branch_name]` | Download branch from remote repo and checkout.                                                                                                                                      |

