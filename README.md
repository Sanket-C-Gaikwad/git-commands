changes made



> What is Git?
Git is a distributed version control system used to track changes in source code during software development.
Version control is used to manage changes to the document or the codebase.

> What's the difference between Git and GitHub?
Git is a version control system, while GitHub is a platform that provides a hosting website for Git repositories and collaboration tools.

> Adding a feature branch:
- git branch
- git checkout -b feature-1
- git checkout main
- git add . (or -a)
- git commit -am "add plus commit, no need of add step"
- git push -u origin feature-1 (push the code upstream to the github new feature branch)

> merging features command:
- git merge main

> Once the featur is merged you call pull the changes to your local repo and delete the featrue if the upstream is setup
- git pull
- git brach -d feature-1
