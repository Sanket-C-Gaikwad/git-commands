> What is Git?
Git is a distributed version control system used to track changes in source code during software development.
Version control is used to manage changes to the document or the codebase.

> Clone repository
- git clone URL

> Open viusal studio code GUI
-  code .\git-repo\

> Initializing a repo
- git init
- git branch -m master main

> staging files
- git add file1.js            # Stages a single file
- git add file1.js file2.js   # Stages multiple files
- git add *.js                # Stages with a pattern
- git add .                   # Stages the current directory and all its content

> How to setup global and local users for the repo
- git config user.name "Your Name"
- git config user.email "youremail@example.com"
- git config --global user.name "Your Name"
- git config --global user.email "youremail@example.com"
- git config user.email
- git config user.name

> Connecting git remote and local
- git remote add origin URL


> Viewing the status
- git status                  # Full status
- git status -s               # Short status


> Committing the staged files
- git commit -m “Message”     # Commits with a one-line message
- git commit                  # Opens the default editor to type a long message
- git commit -am “Message”    # Skipping the stagig stage

> What's the difference between Git and GitHub?
Git is a version control system, while GitHub is a platform that provides a hosting website for Git repositories and collaboration tools.

> Viewing the staged/unstaged changes
- git diff                    # Shows unstaged changes
- git diff --staged           # Shows staged changes
- git diff --cached           # Same as the above


> Adding a feature branch:
- git branch
- git checkout -b feature-1
- git branch --set-upstream-to=origin/feature111
- git checkout main
- git add . (or -a)
- git commit -am "add plus commit, no need of add step"
- git push -u origin feature-1 (push the code upstream to the github new feature branch)

> merge the latest changes from other temam feature to main to keep it up-to-date with respect to others merged feature
- git merge main
- git merge feature-branch  (Switch to main and run this)

> Once the featur is merged you call pull the changes to your local repo and delete the featrue if the upstream is setup
- git pull
- git brach -d feature-1

> Resetting the main brach to previous changes:
- git reset --hard HEAD       (going back to HEAD)
- git reset --hard HEAD^      (going back to the commit before HEAD)
- git reset --hard HEAD~1     (equivalent to "^")
- git reset --hard HEAD~2     (going back two commits before HEAD)

> Logs
- git log

> To reset to a particular commit copy the hash code from log and use below code
- git reset commit-hash-code-here


> What is a repository in Git?
- A repository (repo) is a place where Git stores all the files, history, and metadata for a project.

> How do you initialize a Git repository?
- Use the command: git init

> How do you clone a repository?
- Use the command: git clone <repository_url>

> What is the purpose of the git pull command?
- It fetches changes from a remote repository and merges them into the current branch.

> What is the purpose of the git push command?
- It sends local commits to a remote repository.

> Explain the difference between git merge and git rebase.
- git merge combines branches' histories, creating a new commit that has two parent commits.
- git rebase moves the entire branch to begin on the tip of another branch, resulting in a linear history.

> How do you create a new branch in Git?
- Use the command: git checkout -b <branch_name>

> How do you switch between branches?
- Use the command: git checkout <branch_name>

>> Intermediate question 

> What is a commit in Git?
- A commit is a snapshot of changes made to a repository. It includes a unique identifier, a message, and references to its parent commits.

> How can you undo the last commit, keeping the changes unstaged?
- Use the command: git reset HEAD^

> How can you undo the last commit, keeping the changes staged?
- Use the command: git reset --soft HEAD^

> What is a Git conflict? How do you resolve it?
- A conflict occurs when Git can't automatically merge changes due to overlapping edits in different branches. To resolve, manually edit the conflicting files, then commit the resolved changes.

> Explain the git stash command.
- git stash temporarily stores changes that are not ready to be committed, allowing you to switch branches without committing incomplete work.

> How do you view the commit history of a repository?
- Use the command: git log

> What is the purpose of the .gitignore file?
- It specifies patterns of files and directories that should be ignored by Git.

> How can you remove a file from the Git repository but keep it locally?
- Use the command: git rm --cached <file_name>

> What is the difference between git fetch and git pull?
- git fetch retrieves changes from a remote repository but doesn't merge them.
- git pull fetches and merges changes from a remote repository.

> What is the purpose of rebasing?
- Rebasing allows you to incorporate changes from one branch into another by moving, replaying, or squashing commits.

>> Advanced Git Questions:

> Explain the concept of a Git "rebase workflow."
- The rebase workflow involves frequently updating a feature branch with changes from the main branch by rebasing the feature branch onto the main branch. This maintains a clean and linear history.

> What is a Git tag? How do you create and push tags?
- A tag is a named reference to a specific commit. To create a tag: git tag <tag_name>, and to push tags: git push --tags

> How can you rewrite a commit message of the most recent commit?
- Use the command: git commit --amend

> Explain the difference between a "fast-forward" and "non-fast-forward" merge.
- A fast-forward merge occurs when the target branch's tip is an ancestor of the source branch's tip. A non-fast-forward merge creates a new merge commit, even if the target branch's tip is an ancestor.

> How can you cherry-pick a commit from one branch to another?
- Use the command: git cherry-pick <commit_hash>

> What is a Git hook?
- A Git hook is a script that Git can execute before or after certain events, such as commits, pushes, or merges.

> How do you squash multiple commits into a single commit?
- Use an interactive rebase: git rebase -i HEAD~<number_of_commits>, then change "pick" to "squash" or "s" in the interactive rebase editor.

> Explain the purpose of git bisect and how it works.
- git bisect is used to find the commit that introduced a bug by binary search. It requires identifying a known "good" and "bad" commit, and Git will help you navigate between them to narrow down the culprit.

> What is a Git submodule?
- A submodule is a separate Git repository embedded within another repository. It allows the inclusion of external projects as dependencies.

> How can you revert a commit that has already been pushed to a remote repository?
- Use the command: git revert <commit_hash> to create a new commit that undoes the changes introduced by the specified commit.



> Resolving conflict
> To resolve a merge conflict by discarding the changes made by a specific developer (in this case, 'fzxrwbuz') and commit the changes with the commit message 'yyvtzv merged and favors his solution', you can follow these steps:

Start by checking out the branch where the conflict occurred (e.g., the main branch, assuming that's where you're merging your changes).


- git checkout main
- Then, start the merge process. If you're in the middle of a merge with conflicts, you might have paused at this point. If not, initiate the merge with your feature branch.

- git merge feature-branch
- When you encounter the merge conflict, you can use Git's merge strategy to favor the changes of one side over the other. In this case, you want to favor the main branch ('ours' strategy).

- To favor the main branch, you can use the following command. Replace 'file.txt' with the actual file that has a conflict.

- git checkout --ours file.txt
- This command will choose the version from the main branch, discarding the changes from the feature branch.


- git add file.txt
- Now, commit the changes with the specified commit message:


- git commit -m "yyvtzv merged and favors his solution"
- Finally, complete the merge:


- git merge --continue
- This will finalize the merge, and the changes made by 'fzxrwbuz' will be discarded in favor of the main branch. The commit message 'yyvtzv merged and favors his solution' will be associated with this merge commit.

Remember to replace 'feature-branch' with the actual name of your feature branch, and 'file.txt' with the actual file(s) that have conflicts in your specific situation.
