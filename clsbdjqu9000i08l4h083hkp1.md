---
title: "Day 12 - Cheat-Sheet"
seoTitle: "Git Cheat-Sheet"
datePublished: Wed Feb 07 2024 05:53:55 GMT+0000 (Coordinated Universal Time)
cuid: clsbdjqu9000i08l4h083hkp1
slug: day-12-cheat-sheet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707279434538/6724d533-6995-48ec-b175-1656d003d7ba.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707285203502/dba73d50-1737-4e38-8cc7-b93cec56732c.png
tags: docker, aws, github, kubernetes, git, devops, devsecops, 2articles1week, technical-writing-1, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts. In DevOps, expertise in Linux and Git is paramount. Keeping that in mind this blog will be focusing on creating a concise bundle of commands, what most people call a "Cheat-Sheet".

What's new? The catch here is, every reader has to create their own cheat-sheet from their understanding of Git and GitHub. They can visit the previous blogs for reference and create their own version of their cheat-sheet.

What is the need? Creating our own Cheat sheet will not only help us revise the concepts, but also it'll make our understanding even more crisp and clear.

Along with that a google form will be given below where you can submit your cheat-sheet link, pdf or doc as you wish. And don't forget to share it on LinkedIn or Twitter for others to learn from it too. So without any further ado, let's begin.

## Cheat Sheet

### Initialization Commands

1. Initialize a git repository
    
    ```bash
    git init
    ```
    
2. Clone a GitHub repo to your local machine
    
    ```bash
    git clone <url>
    ```
    
3. Connect to remote repository
    
    ```bash
    git remote add origin <branch>
    ```
    
4. Create a branch
    
    ```bash
    git checkout <branch_name>
    ```
    
5. Create and move to a new branch
    
    ```bash
    git checkout -p <branch_name>
    ```
    
6. List all the branches
    
    ```bash
    git branch
    ```
    
7. Add changes made to a file, also known as staging.
    
    ```bash
    git add <file_in_which_changes_were_made>
    ```
    
8. Add all changed files in the current directory
    
    ```bash
    git add .
    ```
    
9. Commit the changes
    
    ```bash
    git commit -m "commit message"
    ```
    
10. Checking the status.
    
    ```bash
    git status
    ```
    
11. Pushing changes to the remote repository.
    
    ```bash
    git push origin <branch_name>
    ```
    
12. Remove a local git repository
    
    ```bash
    rm -rf .git
    ```
    
13. To configure username to local machine
    
    ```bash
    git config user.name "Github_UserName"
    ```
    
14. To configure email to local machine
    
    ```bash
    git config user.email "GitHub_email"
    ```
    
15. To update local branch with the changes made in the remote repo
    
    ```bash
    git pull -r
    ```
    
16. To get changes from remote repo, but not merge it automatically
    
    ```bash
    git fetch
    ```
    
17. To merge branches
    
    ```bash
    git merge <branch_name_to_be_merged>
    ```
    
18. Check logs like commits etc.
    
    ```bash
    git log
    ```
    
19. To see difference between two commits
    
    ```bash
    git diff <commit1> <commit2>
    ```
    
20. To save your current changes into stash before committing it, in case need to work on other changes and not want to loose the previous changes.
    
    ```bash
    git stash
    ```
    
21. Pop out from stash to dev line
    
    ```bash
    git pop
    ```
    
22. List all the stash
    
    ```bash
    git stash list
    ```
    
23. To see the contents of a stash
    
    ```bash
    git stash show stash@{n}
    ```
    
24. Reset a commit
    
    ```bash
    git reset HEAD~n #no of commits from HEAD
    ```
    
25. Soft reset
    
    ```bash
    git reset --soft HEAD~n
    ```
    
26. Hard reset
    
    ```bash
    git reset --hard HEAD~n
    ```
    
27. Revert the changes made in a commit
    
    ```bash
    git revert <commit_hash>
    ```
    
28. To revert the previous commit
    
    ```bash
    git revert HEAD
    ```
    
29. To see commit history / logs in a concise format
    
    ```bash
    git log --online
    ```
    
30. To see logs in a graphical format
    
    ```bash
    git log --graph
    ```
    
31. Rebase a feature branch onto the latest commit of the main branch
    
    ```bash
    git checkout feature_branch
    git rebase main_branch
    ```
    
32. History of changes made to a specific file
    
    ```bash
    git lof <file>
    ```
    
33. Show the commits on branchA that are not on branchB
    
    ```bash
    git log branchA..branchB
    ```
    
34. Delete file from a project
    
    ```bash
    git rm <file>
    ```
    
35. Move file from one folder to another
    
    ```bash
    git mv [existing-path] [new-path]
    ```
    
36. To cherry-pick a commit
    
    ```bash
    git cherry-pick <commit_hash>
    ```
    
37. To Rename a branch
    
    ```bash
    git checkout -R <old_branch_name> <New_Branch_name>
    ```
    

## Conclusion

Here comes the end of My version of cheat sheet and now its your turn. I've summed up 37 commands starting covering all the corners of Git and GitHub, be it the very basics or be it the advanced one. Go through it and curate your own. I hope this will add value to your learnings.

Submit your cheat-sheet here: [https://forms.gle/om6wLNB3woy7SKwz7](https://forms.gle/om6wLNB3woy7SKwz7)

Ending this with a QUOTE

> Embrace the challenges, master the tools, and transform your obstacles into opportunities. With Linux and Git as your allies, there's no limit to what you can achieve in the world of DevOps.

Happy Learning