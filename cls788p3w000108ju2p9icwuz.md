---
title: "Day 9 - Deep Dive in Git & GitHub"
seoTitle: "Hands On Practice on Git & GitHub "
datePublished: Sun Feb 04 2024 08:14:17 GMT+0000 (Coordinated Universal Time)
cuid: cls788p3w000108ju2p9icwuz
slug: day-9-deep-dive-in-git-github
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ZDwh_sxsX2g/upload/f35e1340e8cd824dced05bfa9d00299c.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1707034384267/2750fb48-9f59-4e78-b096-996632404ab2.png
tags: docker, aws, github, kubernetes, git, devops, 2articles1week, technical-writing-1, devops-articles, gitcommands, devops-journey, 90daysofdevops, trainwithshubham, 90daysofdevops-chanllenge, devopscommunity

---

## Introduction

Welcome to another blog of Building DevOps Engineers. This blog is all about hands on practice of the concepts we learned about Git and GitHub in the past blog. As a part of #90daysofdevops challenge, we have to perform these tasks to showcase our understanding and grasp on the concepts. No worries, the solution will be available by the end of this blog. So without any further ado let's begin.

## Practice Tasks

## Find the answers by your understandings (Shouldn't be copied by internet & used hand-made diagrams) of below questions and Write blog on it.

1. What is Git and why is it important?
    
2. What is difference Between Main Branch and Master Branch??
    
3. Can you explain the difference between Git and GitHub?
    
4. How do you create a new repository on GitHub?
    
5. What is difference between local & remote repository? How to connect local to remote?
    

## Tasks

task-1:

* Set your user name and email address, which will be associated with your commits.
    

task-2:

* Create a repository named "Devops" on GitHub
    
* Connect your local repository to the repository on GitHub.
    
* Create a new file in Devops/Git/Day-02.txt & add some content to it
    
* Push your local commits to the repository on GitHub
    

Note: These steps assume that you have already installed Git on your computer and have created a GitHub account. If you need help with these prerequisites, you can refer to the [day-08](https://hashnode.com/post/cls5th5ug00030ajr83bte5o3)

## Solution

1. **What is Git and why is it important?**
    
    Git is a distributed version control tool that provides us a platform to keep track of the changes made to a file or a set of files.
    
    [I](https://github.com/LondheShubham153/90DaysOfDevOps/blob/ee7c53f276edb02a85a97282027028295be17c04/2023/day08/README.md)t is the most important tool for version control of a project because of it gives us the power to collaborate with others and work on a single or a set of files or projects with ease, revert any unwanted changes made and keep a track of all the changes made with the details of the user who made those changes.
    
2. **What is difference Between Main Branch and Master Branch??**
    
    There's no difference in the Main or the Master Branch. As per the changes made in the year 2022, the default branch was renamed to Main branch. The initial default branch was named Master branch before 2022.
    
3. **Can you explain the difference between Git and GitHub?**
    

| Git | GitHub |
| --- | --- |
| Git is a distributed version control system that is installed in your local machine. | It is a web based distributed version control system supported by Git. |
| It has all the basic features required to manage codebase, version control and supports contributors. | It contains all the basic features of Git along with some advanced features. |
| Not so user friendly. | Very User Friendly |

1. **How do you create a new repository on GitHub?**
    

To Create a new repository on GitHub here are the steps:

Create a GitHub Account first. Click the + sign at the top right corner to create a new repository. Repositories are like your code folders online.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1706946929233/d291a987-d778-4d39-aef4-177a60c84bb9.png align="center")

* Name the Repo and Press Enter. Your repository is created
    

1. **What is difference between local & remote repository? How to connect local to remote?**
    
    A local repository is the repository that is available and stored at your local system or the machine. It is where you add features, create code etc. before merging it to the main directory on the remote.
    
    A Remote repository is a repository located on the GitHub server or any hosted server be it on the cloud or any company's premise. It is a repo where developers push their changes made on a project on their local machine and it gets merged to the main remote repository after approval.
    
    To connect to a remote repository we can use "SSH"( Secured Shell ) or in case of GitHub we can use the command
    
    ```bash
    git remote add <remote_name> <repo_url>
    #e.g. 
    git remote add origin git@github.com:user/repo.git
    ```
    

### Tasks Solution:

### **Task 1: Set User Name and Email Address**

Open your terminal and run the following commands, replacing "github\_userName" and "github\_email" with your actual name and email address:

```bash
git config --global user.name "github_userName"
git config --global user.email "github_email"
```

### **Task 2: Create a Repository on GitHub**

1. Go to GitHub and log in to your account.
    
2. Click the "+" [](https://github.com/)sign in the top right corner and select "New repository."
    
3. Name the repository "Devops" and provide any additional details you'd like.
    
4. Click "Create repository."
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033277027/ae54f5a4-ad8f-44c2-83e0-06b72b5c2fdb.png align="center")
    
    NOTE: To go through each step, visit [Day 8](https://hashnode.com/post/cls5th5ug00030ajr83bte5o3) Blog.
    

### **Task 3: Connect Local Repository to GitHub**

Initialized a git repo and linked it to the remote repo.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033536389/71ba37c8-2af4-4d9f-bd71-0768aacb1d6c.png align="center")

### **Task 4: Create a New File and Add Content**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033861904/1cfe13c3-6156-4d2e-b8d1-88d699fab824.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033821615/efc98742-d01a-4c26-a974-deb9c4d3ab87.png align="center")

### **Task 5: Commit and Push Changes**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033922409/0ced42f5-c7a1-41ff-930f-0ca01ea21465.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707033966599/9f637004-5b38-4008-8f46-7bc52dd1d4a1.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707034007313/77b8f0c0-177e-4bc2-a221-c28a764632e8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707034047091/2775d632-061c-47d6-9cf3-42f20af0aa9d.png align="center")

### Verification

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1707034123092/d2e9f6a8-768e-4d15-accf-7504542ed29b.png align="center")

## Conclusion

In our Day 9 dive into Git and GitHub for DevOps, we unraveled the essence of version control, spotlighting Git's pivotal role in tracking changes and promoting collaboration. We explored the shift from "Master" to "Main" branch, reflecting a nuanced evolution in industry language. The distinction between local Git management and GitHub's collaborative platform became evident with the seamless creation of the "Devops" repository. Emphasizing the crucial link between local and remote repositories, our journey culminated in effortlessly pushing our work to the "Devops" GitHub repository. This exploration equips DevOps engineers with key insights for confident and efficient navigation in the dynamic coding landscape.

Ending it with a quote:

> "In the symphony of collaboration, Git orchestrates the harmony of code, and GitHub provides the stage where innovation takes center stage.

Hope this blog adds value to your learnings. Happy Learning.