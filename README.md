> What is Git?
Git is a distributed version control system used to track changes in source code during software development.
Version control is used to manage changes to the document or the codebase.

> Initializing a repo
- git init

> stagin files
- git add file1.js            # Stages a single file
- git add file1.js file2.js   # Stages multiple files
- git add *.js                # Stages with a pattern
- git add .                   # Stages the current directory and all its content

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
- git checkout main
- git add . (or -a)
- git commit -am "add plus commit, no need of add step"
- git push -u origin feature-1 (push the code upstream to the github new feature branch)

> merg the latest changes from other temam feature to main to keep it up-to-date with respect to others merged feature
- git merge main

> Once the featur is merged you call pull the changes to your local repo and delete the featrue if the upstream is setup
- git pull
- git brach -d feature-1

> Resetting the main brach to previous changes:
- git reset --hard HEAD       (going back to HEAD)
- git reset --hard HEAD^      (going back to the commit before HEAD)
- git reset --hard HEAD~1     (equivalent to "^")
- git reset --hard HEAD~2     (going back two commits before HEAD)