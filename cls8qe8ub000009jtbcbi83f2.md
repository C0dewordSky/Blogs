---
title: "Day 10 - Advance Git & GitHub"
seoTitle: "Advance Git & GitHub "
datePublished: Mon Feb 05 2024 09:30:15 GMT+0000 (Coordinated Universal Time)
cuid: cls8qe8ub000009jtbcbi83f2
slug: day-10-advance-git-github
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707116957116/41587d49-57e9-46e8-9614-31e63f6b0ee2.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707125381864/53ffc986-cab2-4ca7-8144-478694103b94.png
tags: linux, docker, aws, github, git, devops, hashnode, 2articles1week, technical-writing-1, devops-articles, gitcommands, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge

---

## Introduction

Welcome DevOps enthusiasts. Now we're headed to dive deep into the world of Git and GitHub and learn some advanced concepts. In this blog we will gain knowledge on some advanced features like Reverting, Reset, Rebase and merge. Also we'll understand the significance of Branches.

That's not it, we'll be carry forwarding our tradition of interactive blogs and by the end we'll be solving some hands on tasks for better understanding of the concepts. Stuck somewhere? No worries, I got you covered with the Solution section section at the end. So without any further delays let's begin learning.

## Git Branching

![](https://www.nobledesktop.com/image/gitresources/git-branches-merge.png align="center")

### What is Git Branch?

A branch in Git is the line of development. In the normal scenario, we have a default branch ("master" or "main" ) and then we have other sub branches called the <mark>feature branch</mark>.

The Feature branch are used to push code that contains changes from the local repository to the remote repository without disturbing the line of development i.e. the default branch.

These sub branches can later on get merged to the default branch if it meets the requirements of the project.

### Naming Convention of Branches:

A branch can be named on the purpose they solve. Here's a table explaining the ideal naming convention that should be followed:

| Branch Name | Purpose It solves |
| --- | --- |
| Feature Branch | For changes like adding features or updating a feature. |
| Bugfix branch | For commits containing Bug Fixes |
| Release branch | For Newer Version |
| Hotfix branch | For critical issues or bugs in a production environment |

### Commands:

1. To Check the current branch
    
    ```bash
    git branch
    ```
    
2. To Create a branch
    
    ```bash
    git branch <name_of_branch>
    ```
    
3. To Checkout and Create a branch at the same time
    
    ```bash
    git checkout -b <name_of_branch>
    ```
    
4. To list all branches
    
    ```bash
    git branch -a
    ```
    
5. To Delete a branch
    
    ```bash
    git checkout -d <name_of_branch>
    ```
    

## Git Revert and Reset

### What is Git Revert?

![](https://images.datacamp.com/image/upload/v1671196209/Diagram_of_Revert_Before_and_After_4b427cf59b.png align="center")

Git Revert is the command that is used for undoing changes to a repository's commit history.

Git Reverts creates a new commit in which the changes made in the previous commit are reverted or Undone. By doing this, it preserves the commit history and users can access to the past commit if needed.

NOTE: It does not delete the commit.

### Commands:

1. To Revert a change
    
    ```bash
    git revert <Hash_code_of_the_commit>
    ```
    
2. To Revert the previous commit
    
    ```bash
    git revert HEAD
    ```
    

### What is Git Reset?

![](https://res.cloudinary.com/practicaldev/image/fetch/s--x1oDKltr--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://cl.ly/063v3m0l2X3b/Image%25202018-05-21%2520at%252010.56.45%2520AM.png align="center")

This is a similar command as compared to git revert but the catch here is that it creates a commit undoing the changes and DELETES the commit which needs to be undone.

There are two types of Resetting:

* <mark>--soft</mark> : It resets the commit but still we can have the access to the commit in the git history.
    
* <mark>--hard</mark> : It resets the commit and deletes it. This way we don't have any access to the history and the commit cannot be accessed.
    

### Commands:

```bash
git reset --soft HEAD~n 
git reser --hard HEAD~n 
```

Where **<mark>n</mark>** is the number of commits respectively from the head we want to reset.

## Git Rebase and Merge

### What is git Rebase?

Rebasing is the process of moving or combining a sequence of commits to a new base commit. Rebasing is most useful and easily visualized in the context of a feature branching workflow. The general process can be visualized as the following:

![Git rebase](https://wac-cdn.atlassian.com/dam/jcr:4e576671-1b7f-43db-afb5-cf8db8df8e4a/01%20What%20is%20git%20rebase.svg?cdnVersion=1427 align="left")

From the above we can conclude, rebasing is changing the base of your branch from one commit to another making it appear as if you'd created your branch from a different commit.

Git accomplishes this by creating new commits and applying them to the specified base.

NOTE: It's very important to understand that even though the branch looks the same, it's composed of entirely new commits.

Read more about Rebasing, [Here](https://git-scm.com/docs/git-rebase).

### What is Git Merge?

Git merge is a command used to merge two or more branches into the Main or Default branch.

Say we have a new branch feature that is based off the `main` branch. We now want to merge this feature branch into `main`.

![](https://wac-cdn.atlassian.com/dam/jcr:7afd8460-b7bf-4c42-b997-4f5cf24f21e8/01%20Branch-2%20kopiera.png?cdnVersion=1427 align="center")

Calling the `git merge` command will merge the specified branch feature into the main branch.

![](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=1427 align="center")

Read more, [Here](https://www.atlassian.com/git/tutorials/using-branches/git-merge).

### Commands:

```bash
git merge
```

## Hands On Practice

## Task 1:

Add a text file called version01.txt inside the Devops/Git/ with “This is first feature of our application” written inside. This should be in a branch coming from `master`, \[hint try `git checkout -b dev`\], switch to `dev` branch ( Make sure your commit message will reflect as "Added new feature").

\[Hint use your knowledge of creating branches and Git commit command\]

* version01.txt should reflect at local repo first followed by Remote repo for review. \[Hint use your knowledge of Git push and git pull commands here\]
    

Add new commit in `dev` branch after adding below mentioned content in Devops/Git/version01.txt: While writing the file make sure you write these lines

* 1st line&gt;&gt; This is the bug fix in development branch
    
* Commit this with message “ Added feature2 in development branch”
    
* 2nd line&gt;&gt; This is gadbad code
    
* Commit this with message “ Added feature3 in development branch
    
* 3rd line&gt;&gt; This feature will gadbad everything from now.
    
* Commit with message “ Added feature4 in development branch
    

Restore the file to a previous version where the content should be “This is the bug fix in development branch” \[Hint use git revert or reset according to your knowledge\]

## Task 2:

* Demonstrate the concept of branches with 2 or more branches with screenshot.
    
* add some changes to `dev` branch and merge that branch in `master`
    
* as a practice try git rebase too, see what difference you get.
    

## Solution

### Task 1 :

* Created version01.txt file, made changes and reflecting it into the remote repo.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707121896758/09aaea58-fc7b-47f0-bdd4-08fbb35f5666.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707121992637/e3836d5e-9cce-43fc-9f4b-e7ac9bbada8f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122153420/dd3889b2-43eb-4228-836d-10e92770249a.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122304450/99a35d5f-4847-4016-bc26-7b47f5a1e789.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122334679/bc758540-ea57-4969-a978-bf9e21448b24.png align="center")

* Making Bug Fixes chances, committing and Pushing it the remote repository
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122516438/3113e4ff-9eaa-4b2c-bc99-dcc1dea71dbf.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122617491/fecd228a-90b5-4814-b66a-0cb2aafb68e0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707122694177/c885df02-990d-41ab-82a4-f808d7f0b32a.png align="center")

* Restoring the file to a previous version where the content should be “This is the bug fix in development branch”. We'll be using git reset command followed by --hard flag.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707123834792/83a071b1-84b7-426b-bc43-763680d6b74a.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707124270819/ccddd6c8-f0fe-481f-85ef-3ccfdb259239.png align="center")

* Now Merging The Commits
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707124465346/8691beee-f6af-430d-8acd-1cd29fa6ead9.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707124476147/65a329de-7b08-4c75-8d99-11100284142b.png align="center")

And Here we can see the branches are merged.

### Task 2 :

* Concept of Branch vis screenshot
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707121992637/e3836d5e-9cce-43fc-9f4b-e7ac9bbada8f.png align="center")
    
* Changes to dev branch and merged to main branch
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707124270819/ccddd6c8-f0fe-481f-85ef-3ccfdb259239.png align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707124465346/8691beee-f6af-430d-8acd-1cd29fa6ead9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707125139193/1f25ac77-74c1-45a1-88a4-dfbbc338ecae.png align="center")

## Conclusion

So here comes the end of this blog. In summary we covered the major concepts of branch, naming convention of branches, commands and also understood the differences between Git Revert, Git Reset and Git Rebase and Git Merge. Along with that the hands on practice section acted as a cherry on the cake making our learning even more fun and robust.

Ending this with a quote

> In theory, theory and practice are the same. In practice, they’re not.

Happy Learning.