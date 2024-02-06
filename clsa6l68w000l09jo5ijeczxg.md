---
title: "Day 11 - Advance Git and GitHub Part -2"
seoTitle: "Advance Git and GitHub Part -2"
datePublished: Tue Feb 06 2024 09:51:18 GMT+0000 (Coordinated Universal Time)
cuid: clsa6l68w000l09jo5ijeczxg
slug: day-11-advance-git-and-github-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1707207255753/43d8900d-87c1-4536-88ba-3e5707f25064.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707213046167/767c9c26-14ef-4b0f-b636-47dd60cb2269.png
tags: linux, docker, aws, github, kubernetes, git, devops, hashnode, 2articles1week, devops-articles, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome DevOps enthusiasts. In this blog we're gonna learn more about advanced but less common Git commands. From Git Stash to cherry picking to Resolving Merge Conflicts, this blog got you covered. We'll understand these in the simplest of ways followed by hands on practice by the end to fortify your concepts. So without any further delay, lets learn.

## Git Stash

### What is git stash?

Git stash is a command that is used to temporarily shelf a changes you made, work on other changes and then come back to it later on. It is used when you want to switch branches or work on a different task without committing the current changes that you made.

Basically Git Stash preserves your changes before commit, without worrying about losing your progress, in case there's a call for another task to be done ASAP.

![](https://miro.medium.com/v2/resize:fit:1200/1*Eced1qZ6rVz0npKAvJKJgw.png align="center")

### Use Case

Suppose, you're working on a feature for your project and suddenly your boss orders you to fix a bug on the production line ASAP.

Now, you've made some changes to your code, but they're not quite ready to be committed yet. You don't want to lose your progress, but you also need to switch over to the main branch ASAP to help out.

This is where Git stash comes to your rescue. Using `git stash` command you stash away your current changes, like putting them in a little box for safekeeping. And now you're fee to fix the bug without worrying to loose your progress on the feature.

### Commands

1. Stashing or Removing from working directory
    
    ```bash
    git stash
    ```
    
2. Getting the changes back in the area
    
    ```bash
    git stash pop
    ```
    
3. List all the stashes
    
    ```bash
    git stash list
    ```
    
4. To see contents of a stash
    
    ```bash
    git stash show stash@{n}
    ```
    
    where,
    
    **git stash show**: command for showing content
    
    **stash@{n}**: Specifies which stash you want to inspect. The `{n}` represents the index of the stash, where `0` is the most recent stash, `1` is the one before that, and so on.
    

## Cherry Pick

### What is cherry-pick ?

cherry-pick is the command used for merging a specific commit into the line of development. As the name suggests it points to a specific commit using the hashcode and then get it merged into the main/master branch.

When you're working on different branches in Git, sometimes you come across a commit on one branch that you just have to have on another branch—maybe it's a fix or a feature that's exactly what you need. That's where `git cherry-pick` comes in!

It's like picking up the juiciest cherry from a box.

### Use Cases:

1. **Debugging in Branches**: Imagine you have two branches, development and debugging. You fixed a critical bug in the bug fix branch, and now you need to apply that fix on your development branch without all the other changes. Cherry picking a commit that contains a bug fix allows you to select only that fix together in development with no changes other than the bug fix.
    
2. **Feature Backporting**: Let’s say you were working on a new feature in the feature branch, feature-x, but realize that you need this feature immediately in your stable production branch, master Instead of merging the entire feature-x branch made into a master, which may include unfinished work or other changes that are not ready for release, you can cherry-pick specific commit(s) of the complete feature and apply them to master
    
3. **Selective Code Review**: While in code review, you can see your commits to a feature branch that is particularly well written or solves a problem in the most appropriate way.
    
4. **Undoing changes**: If you want to undo changes made by a particular commit on a branch, you can use git cherry-pick to roll back that commit in reverse order to the same branch this this changes caused by that commit very thoroughly, with no errors or unwanted changes affecting the rest of the branch history Provides a targeted approach to handling.
    
5. **Managing Release Branches**: In a project with multiple release branches you may need to ensure that each release branch has specific bug fixes or updates applied, making them independent Cherry-picking to allow commits to be applied in the option selected on each release branch as needed, ensuring that repairs are extended with no unrelated changes
    

These are a few Use cases of how `git cherry-pick` can be used to selectively apply commits from one branch to another, providing flexibility and control over the development process.

### Commands

1. To cherry-pick a command
    
    ```bash
    git cherry-pick
    ```
    

## Resolving Conflicts

### What is a conflict?

![](https://i.imgflip.com/5f9hsp.jpg align="center")

Conflicts can occur when you merge or rebase branches that have diverged, and you need to manually resolve the conflicts before git can proceed with the merge/rebase.

Git status command shows the files that have conflicts.

Git diff command shows the difference between the conflicting versions.

Git add command is used to add the resolved files.

![](https://www2.stat.duke.edu/courses/Fall19/sta199.001/slides/lab-slides/img/03/merge-conflict-identifiers.png align="center")

## Hands On Practice

# Task Overview

* Create a new branch and make some changes to it.
    
* Use git stash to save the changes without committing them.
    
* Switch to a different branch, make some changes and commit them.
    
* Use git stash pop to bring the changes back and apply them on top of the new commits.
    

# Task-01

* In version01.txt of development branch add below lines after “This is the bug fix in development branch” that you added in [Day10](https://hashnode.com/post/cls8qe8ub000009jtbcbi83f2) and reverted to this commit.
    
* Line2&gt;&gt; After bug fixing, this is the new feature with minor alteration”
    
    Commit this with message “ Added feature2.1 in development branch”
    
* Line3&gt;&gt; This is the advancement of previous feature
    
    Commit this with message “ Added feature2.2 in development branch”
    
* Line4&gt;&gt; Feature 2 is completed and ready for release
    
    Commit this with message “ Feature2 completed”
    
* All these commits messages should be reflected in Production branch too which will come out from Master branch (Hint: try rebase).
    
    Read [Day 10](https://hashnode.com/post/cls8qe8ub000009jtbcbi83f2) for detailed solution.
    

# Task-02

* In Production branch Cherry pick Commit “Added feature2.2 in development branch” and added below lines in it:
    
* Line to be added after Line3&gt;&gt; This is the advancement of previous feature
    
* Line4&gt;&gt;Added few more changes to make it more optimized.
    
* Commit: Optimized the feature
    

## Solution

### Task - 01:

1. Committing all the changes individually.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707211296276/90e5a226-14b2-4db3-a1ee-d68ba9ea3f9f.png align="center")
    
2. Pushing it to dev branch.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707211350276/45973dec-9cb9-41af-9cfd-729a8431e1bb.png align="center")
    
3. Rebasing to the main branch
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707211624789/aeae149e-b1b4-44eb-88f2-10ef5f41b7d3.png align="center")
    
4. We have to push the changes and then it can be seen on the main branch on GitHub.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707211711951/0eff84bf-4600-4d8a-a573-51a9b63743b3.png align="center")
    

### Task - 02 :

1. Cherry picking Commit “Added feature2.2 in development branch
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212458367/4b6fa135-02f6-4922-9bae-37a4e9d0a07f.png align="center")
    
2. Resolved the merge conflict and made changes and pushed the code to GitHub.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212500081/2de49ed9-141e-4756-9b2d-f2b8f95ace21.png align="center")
    
3. GitHub main branch showing changes made after cherry picking
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212569048/6eb625b3-bb9a-434e-8107-6f81c8727771.png align="center")
    
4. The Working Tree of the repository
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707212770161/fb80ef89-65a9-41ce-980d-e1bbe2ded4d4.png align="center")
    

## Conclusion

So here comes the end of this blog. In summary we covered the major concepts of Git Stash, Cherry-Picking and resolving conflict. Along with that the hands on practice section acted as a cherry on the cake making our concepts even more fun and robust.

> Believe you can and you're halfway there. - Theodore Roosevelt

Happy Learning.